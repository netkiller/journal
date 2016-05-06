---
layout: post
title:  "一次切割日志引发的血案"
date:   2016-05-05 17:00:00
categories: log
---

一次切割日志引发的血案
-----

很多应用程序会产生日志，有些程序已经实现了日志切割，一般是每天一个文件。但有时这个切割并不能满足我们的需求，例如我们需要颗粒度更细的切割。

切割日志的目的是什么？

1. 日志尺寸过大
1. 便于分析
1. 切割后归档，或者导入日志平台

切割日志基本两种方法：

1. 手工或者 shell
1. 工具,例如logrotate，传统的cronolog

日志切割方案网上有很多，很多运维也是参考这些方案进行配置，网上的例子不完全都是对的，可能你用了很多年配置方案是错误的。
没有出现故障是侥幸，因为笔者15年前就在此处栽过，由于日志太大，我便清空了日志，以为程序仍然会继续写入，最后直到服务器崩溃。
最近发现很多新手再谈cronolog，我便想起当前发生的故障，有必要跟大家分享。

首先日志是可以切割的，网上的例子理论上也是可行，但我们不能不求甚解，稀里糊涂的用下去。

我们首先了解一下日志是怎么产生的，那种日志可以切割，那些日志不能切割，为什么不能切割，如果需要切割日志怎么处理？

### 首先日志是怎么产生的

日志生命周期，创建/打开日志文件，追加日志记录，关闭日志文件。请看下面伪代码。

{% highlight bash %}

main (){

	f = open(/tmp/prog.log)
	...
	...
	f.append('DEBUG .............')
	...
	f.append('INFO .............')
	...
	f.append('WARN .............')
	
	f.close()

}

{% endhighlight %}

这个程序是顺序运行，每次运行都会经历，打开日志文件，追加日志记录，关闭日志文件，一个日志生命周期结束。
在完成日志生命周后，你就可以切割日志了。因为f.close()后日志文件已经被释放。

再看下面的程序

{% highlight python %}
main (){
	f = open(/tmp/prog.log)
	loop{
		...
		...
		f.append('DEBUG .............')
		...
		f.append('INFO .............')
		...
		f.append('WARN .............')
		
		if(quit){
			break
		}
	}
	f.close()

}
{% endhighlight %}

这个程序就不同了，程序运行，打开日志文件，然后进入无穷循环，期间不断写入日志，知道接到重载命令才会关闭日志。
那么这个程序你就不能随便切割日志。你一旦修改了日志文件，程序将不能在写入日志到文件中。
这个程序切割日志的过程是这样的

{% highlight python %}
split loop {
	prog run
	prog quit && mv /tmp/prog.log /tmp/prog.2016-05-05.log
	
}
{% endhighlight %}


再看下面的程序

{% highlight bash %}
main (){
	loop{
		f = open(/tmp/prog.log)
		loop{
			...
			...
			f.append('DEBUG .............')
			...
			f.append('INFO .............')
			...
			f.append('WARN .............')
			
			if(reload){
				break
			}
		}
		f.close()
	}
}
{% endhighlight %}

这个程序多了一层循环，并加入了重载功能。这个程序怎样切割日志呢：

{% highlight bash %}
split loop {
	prog run
	mv /tmp/prog.log /tmp/prog.YYYY-MM-DD.log
	prog reload 
}

{% endhighlight %}

如果你是程序猿，这个程序可以优化一下，一了百了，就是在reload 的时候重新创建或打开日志。

{% highlight bash %}
main (){
	loop{
		f = open(/tmp/prog.YYYY-MM-DD.log)
		loop{
			...
			...
			f.append('DEBUG .............')
			...
			f.append('INFO .............')
			...
			f.append('WARN .............')
			
			if(reload){
				break
			}
		}
		f.close()
	}
}
{% endhighlight %}

### 还有一种情况，你会问为什么不这么写？

{% highlight bash %}
prog {

	log(type, msg){
		f = open(/tmp/prog.YYYY-MM-DD.log)
		f.append(type, msg)
		f.close()
	}
	
	main(){
		...
		...
		log('INFO','..............')
		...
		...
		log('DEBUG','..............')
		...
		...
	}

}
{% endhighlight %}

这种代码的适应性非常强，但牺牲了IO性能，如果平凡打开/关闭文件同时进行写IO操作，这样的程序很难实现高并发。
所以很多高并发的程序，只会打开一次日志文件（追加模式），不会再运行期间关闭日志文件，直到进程发出退出信号。

让我们看个究竟
-----

我们手工模拟一次日志分割的过程，首先开启三个Shell终端。

### 第一种情况，日志文件被重命名

终端一，模拟打开日志文件

{% highlight bash %}
[root@www.netkiller.cn ~]# cat > /tmp/test.log
{% endhighlight %}

终端二，重命名文件

{% highlight bash %}
[root@www.netkiller.cn ~]# mv /tmp/test.log /tmp/test.2016.05.05.log
{% endhighlight %}

终端一，输入一些内容然后按下Ctrl+D 保存文件
{% highlight bash %}
[root@www.netkiller.cn ~]# cat > /tmp/test.log
Helloworld
Ctrl + D

[root@www.netkiller.cn ~]# cat /tmp/test.log
cat: /tmp/test.log: No such file or directory
{% endhighlight %}

### 第二种情况，日志文件被删除

终端一，模拟打开日志文件
{% highlight bash %}
[root@www.netkiller.cn ~]# cat > /tmp/test.log
{% endhighlight %}

终端二，使用lsof查看文件的打开情况
{% highlight bash %}
[root@www.netkiller.cn ~]# lsof | grep /tmp/test.log
cat       20032           root    1w      REG              253,1          0     288466 /tmp/test.log
{% endhighlight %}

终端三，删除日志文件
{% highlight bash %}
[root@www.netkiller.cn ~]# rm -rf /tmp/test.log 
{% endhighlight %}

终端二，查看日志的状态，你能看到 deleted
{% highlight bash %}
[root@www.netkiller.cn ~]# lsof | grep /tmp/test.log
cat        5269           root    1w      REG              253,1          0     277445 /tmp/test.log (deleted)
{% endhighlight %}

终端一，回到终端一种，继续写入一些内容并保存，然后查看日志文件是否有日志记录被写入
{% highlight bash %}
[root@www.netkiller.cn ~]# cat > /tmp/test.log
Helloworld
^D

[root@www.netkiller.cn ~]# cat /tmp/test.log
cat: /tmp/test.log: No such file or directory
{% endhighlight %}

经过上面两个实验，你应该明白了在日志打开期间对日志文件做重命名或者删除都会造成日志记录的写入失败。

### 第三种情况，日志没有被删除，也没有被重命名，而是被其他程序做了修改

第一步，终端窗口一中创建一个文件，文件写入一些字符串，这里写入 “one”，然后查看是否成功写入。
{% highlight bash %}
[root@www.netkiller.cn ~]# echo one > /tmp/test.log
[root@www.netkiller.cn ~]# cat /tmp/test.log
one
{% endhighlight %}
上面我们可以看到/tmp/test.log文件成功写入一个字符串"one"

第二步，开始追加一些字符串
{% highlight bash %}
[root@www.netkiller.cn ~]# cat > /tmp/test.log
two
{% endhighlight %}
先不要保存（不要发出^D）

第三部，在终端二窗口中清空这个文件
{% highlight bash %}
[root@www.netkiller.cn ~]# > /tmp/test.log 
[root@www.netkiller.cn ~]# cat /tmp/test.log
{% endhighlight %}
通过cat查看/tmp/test.log文件，什么也没也表示操作成功。


第四步，完成字符串追加，使用Ctrl+D保存文件，最后使用cat /tmp/test.log 查看内容。
{% highlight bash %}
[root@www.netkiller.cn ~]# cat > /tmp/test.log
two

[root@www.netkiller.cn ~]# cat /tmp/test.log
{% endhighlight %}

你会发现/tmp/test.log文件中没有写入任何内容。这表示在日志的访问期间，如果其他程序修改了该日志文件，原来的程序将无法再写入日志。

让我们再来一次，看个究竟

终端一，创建并追加字符串到日志文件中

{% highlight bash %}
# echo one > /tmp/test.log
# cat /tmp/test.log
one
# cat >> /tmp/test.log
two
{% endhighlight %}
记得不要保存


终端二，使用lsof查看文件的打开情况
{% highlight bash %}
# lsof | grep /tmp/test.log
cat       22631           root    1w      REG              253,1          0     277445 /tmp/test.log
{% endhighlight %}

终端三，开启另一个程序追加字符串到日志文件中
{% highlight bash %}
# cat >> /tmp/test.log 
three
{% endhighlight %}
先不要保存（不要发出^D)

终端二，查看文件的打开情况
{% highlight bash %}
# lsof | grep /tmp/test.log
cat       22631           root    1w      REG              253,1          0     277445 /tmp/test.log
cat       23350           root    1w      REG              253,1          0     277445 /tmp/test.log
{% endhighlight %}

终端三，保存three字符串
{% highlight bash %}
# cat >> /tmp/test.log 
three
^D

# cat /tmp/test.log 
three
{% endhighlight %}

回到终端一，继续保存内容
{% highlight bash %}
# cat > /tmp/test.log
two
^D

# cat /tmp/test.log
two
e
{% endhighlight %}

出现新的行情况了，two报道最上面去了，这是因为打开文件默认文件指针是页首，它不知道最后一次文件写入的位置。

你可以反复实验，结果相同。

{% highlight bash %}
# cat /tmp/test.log
two
e
four
five
{% endhighlight %}

我为什么没有使用  echo  "five" >> /tmp/test.log 这种方式追加呢？因为 cat 重定向后只要不发出^D就不会保存文件，而echo是打开文件，获取文件尾部位置，然后追加，最后关闭文件。



经典案例分析
-----

### Nginx 

{% highlight bash %}
[root@www.netkiller.cn ~]# cat /etc/logrotate.d/nginx
/var/log/nginx/*.log {
        daily
        missingok
        rotate 52
        compress
        delaycompress
        notifempty
        create 640 nginx adm
        sharedscripts
        postrotate
                [ -f /var/run/nginx.pid ] && kill -USR1 `cat /var/run/nginx.pid`
        endscript
}
{% endhighlight %}

nginx 日志切割后会运行 kill -USR1 这个让nginx 重新创建日志文件或者夺回日志文件的操作权。

怎样监控日志
-----

那么怎样监控日志被删除，写入权被其他程序夺取？对于程序猿一定很关注这个问题。下面我们讲解怎么监控日志。

Linux 系统可以使用 inotify 开发包来监控文件的状态变化，包括开打，写入，修改权限等等。

你需要启动一个进程或者线程监控日志文件的变化，以便随时reload 你的主程序。

{% highlight bash %}
prog {
	sign = null
	logfile = /var/log/your.log
	
	thread monitor {
		inotify logfile {
			sign = reload
		}
	}
	thread worker {
		loop{		
			f = open(logfile)
			loop{
				f.append(....)
				
				if(sign == reload)
				{
					break
				}
			}
			f.close()		
		}
	}
	main(){
		monitor.start()
		worker.start()
	}

}
{% endhighlight %}

不知你是否看懂，简单的说就是两个并行运行的程序，一个负责日志监控，一个负责干活，一旦日志发生变化就通知主程序 reload。
至于使用进程还是线程去实现，取决于你熟悉那种语言或者你擅长的技术。

总结
-----

小小的日志文件有如此大的学问，目前很多应用程序写的比较健壮，能够判断出当前日志被删除，改写。程序运行中能够在创建丢失的日志文件，当日志被其他程序改写后，能够夺回写入权。
但这样的程序会影响程序并发性能，鱼和熊掌不能兼得。看了这篇文章我想你应该对日志有了全面了解，也会在接下来的工作中谨慎处理日志。

看了本文不打赏都对不起党跟人民呵呵：）