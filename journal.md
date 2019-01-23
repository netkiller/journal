---
layout: page
title: Journal
permalink: /journal/
---

# journal

*  {% for post in site.journal %}
*  {{ post.date \| date: "%b %-d, %Y" }} [{{ post.title }}](https://github.com/netkiller/journal/tree/1f67b9300d493780b7df5c01a6af57e4c24e7b8a/%7B%7B%20post.url%20%7C%20prepend:%20site.baseurl%20%7D%7D)
*  {% endfor %}

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <ol>
          <li><a href="http://www.netkiller.cn/journal/php.mq.html">PHP高级编程之消息队列</a>[2015-10-19]</li>
          <li><a href="http://www.netkiller.cn/journal/php.daemon.html">PHP高级编程之守护进程</a>[2015-10-21]</li>
          <li><a href="http://www.netkiller.cn/journal/ssi.html">SSL证书卸载与SSI高级应用</a>
          </li>
          <li><a href="http://www.netkiller.cn/journal/os.systemd.html">跟我学 systemd</a>
          </li>
          <li><a href="http://www.netkiller.cn/journal/phalcon.spring.html">Phalcon vs Spring</a>
          </li>
          <li><a href="http://www.netkiller.cn/journal/java.ant.html">Apache Ant 实现自动化部署</a>
          </li>
          <li><a href="http://www.netkiller.cn/journal/network.ios.html">网络设备配置管理与版本控制</a>[2014-12-25]</li>
          <li><a href="http://www.netkiller.cn/journal/security.implants.html">植入式攻击入侵检测解决方案</a>[2014-12-24]</li>
          <li><a href="http://www.netkiller.cn/journal/shell.history.html">Shell 历史记录异地留痕审计与监控</a>[2014-12-24]</li>
          <li><a href="http://www.netkiller.cn/journal/mysql.struct.html">数据库结构版本控制</a>[2014-12-17]</li>
          <li><a href="http://www.netkiller.cn/journal/log.html">日志中心</a>[2014-12-16]</li>
          <li><a href="http://www.netkiller.cn/journal/trader.html">贵金属交易系统异地灾备方案</a>[2014-12-2]</li>
          <li><a href="http://www.netkiller.cn/journal/scheduler.html">分布式计划任务设计与实现</a>[2014-09-30]</li>
          <li><a href="http://www.netkiller.cn/journal/cvs.html">CVS开发框架</a>[2014-09-28]</li>
          <li><a href="http://www.netkiller.cn/journal/fishbone.html">因果图在运维工作中的应用</a>[2014-09-26]</li>
          <li><a href="http://www.netkiller.cn/journal/glusterfs.html">Glusterfs 安装于配置</a>[2014-09-23]</li>
          <li><a href="http://www.netkiller.cn/journal/mysql.security.html">数据库记录安全解决方案</a> |
            <a
            href="http://www.netkiller.cn/journal/mysql.security.en.html">[EN]</a>[2014-08-19]</li>
          <li><a href="http://www.netkiller.cn/journal/token.html">Linux Token Auth</a>[2014-08-01]</li>
          <li><a href="http://www.netkiller.cn/journal/freebsd.php.html">FreeBSD 10 + Nginx 1.4.4 + PHP 5.5.9 + MySQL 5.6.15</a>[2014-02-12]</li>
          <li><a href="http://www.netkiller.cn/journal/cache.html">Web Cache</a>[2014-02-28]</li>
          <li><a href="http://www.netkiller.cn/journal/php.thread.html">PHP 高级编程之多线程</a>[2014-03-12]</li>
          <li><a href="http://www.netkiller.cn/journal/image.html">Image 优化方案</a>[2014-04-21]</li>
          <li><a href="http://www.netkiller.cn/journal/mysql.parallel.html">MySQL 大数据操作注意事项</a>[2014-05-16]</li>
          <li><a href="http://www.netkiller.cn/journal/rpm.html">怎样制作RPM包</a>[2013-04-18]</li>
          <li><a href="http://www.netkiller.cn/journal/mysql.plugin.image.html">数据库与图片完美解决方案</a>[2013-05-15]</li>
          <li><a href="http://www.netkiller.cn/journal/setup.html">CentOS 6.4 + nginx-1.2.5 + php-5.4.15 + MySQL-5.5.31</a> [2013-05-30]</li>
          <li><a href="http://www.netkiller.cn/journal/tomcat.html">Tomcat 安全配置与性能优化</a> [2013-07-23]</li>
          <li><a href="http://www.netkiller.cn/journal/security.html">Linux 系统安全与优化配置</a> [2013-07-25]</li>
          <li><a href="http://www.netkiller.cn/journal/refresh.html">网站防刷新方案</a> [2013-09-26]</li>
          <li><a href="http://www.netkiller.cn/journal/db.restore.html">数据库恢复方案</a> [2013-09-27]</li>
          <li><a href="http://www.netkiller.cn/journal/mysql.plugin.fifo.html">数据库进程间通信解决方案IPC</a> [2013-12-16]</li>
          <li><a href="http://www.netkiller.cn/journal/mysql.plugin.mq.html">数据库进程间通信解决方案RPC</a> [2013-12-31]</li>
          <li>[2012-12-04]<a href="http://www.netkiller.cn/journal/utility.html">运维常用再现工具</a>
          </li>
          <li>[2012-01-05]<a href="http://www.netkiller.cn/journal/syslog.html">Python Syslog Server</a>
          </li>
          <li>[2012-01-06]<a href="http://www.netkiller.cn/journal/daemon.html">Linux 应用程序开发入门</a>
          </li>
          <li>[2012-03-06]<a href="http://www.netkiller.cn/journal/security.php.html">PHP 安全与性能</a>
          </li>
          <li>[2012-03-08]<a href="http://www.netkiller.cn/journal/security.db.html">Linux 系统与数据库安全</a>
          </li>
          <li>[2012-07-26]<a href="http://www.netkiller.cn/journal/logfw.html">access.log top10 IP屏蔽脚本</a>
          </li>
          <li>[2012-07-26]<a href="http://www.netkiller.cn/journal/appfirewall.html">应用软件防火墙设计与实现方法</a>
          </li>
          <li>[2012-08-09]<a href="http://www.netkiller.cn/journal/shell.html">Shell实用实例参考</a>
          </li>
          <li>[2012-08-16]<a href="http://www.netkiller.cn/journal/static.html">网站静态内容出版解决方案</a>
          </li>
          <li><a href="http://www.netkiller.cn/journal/iptables.html">IPTABLES 面向对象封装</a>[2011-12-21]</li>
          <li><a href="http://www.netkiller.cn/journal/spider.html">Python Spider 爬虫实例</a>[2011-12-28]</li>
          <li><a href="http://www.netkiller.cn/journal/fault.html">网络故障分析</a>[2011-12-31]</li>
        </ol>
        <p>OSChina: <a href="http://my.oschina.net/neochen/">http://my.oschina.net/neochen/</a>
        </p>
        <p>ITEYE: <a href="http://netkiller-github-com.iteye.com">http://netkiller-github-com.iteye.com</a>
        </p>
        <p>51CTO: <a href="http://rline.blog.51cto.com/">http://rline.blog.51cto.com/</a>|
          <a
          href="http://g.51cto.com/netkiller">http://g.51cto.com/netkiller</a>
        </p>
        <p>Twitter: <a href="http://twitter.com/bg7nyt">http://twitter.com/bg7nyt</a>
        </p>
        <p>Digg: <a href="http://www.digg.com/netkiller">http://www.digg.com/netkiller</a>
        </p>
        <p>Facebook: <a href="https://www.facebook.com/bg7nyt">https://www.facebook.com/bg7nyt</a>
        </p>
        <p>LinkedIn: <a href="http://cn.linkedin.com/in/netkiller">http://cn.linkedin.com/in/netkiller</a>
        </p>
        <p>Flickr: <a href="http://www.flickr.com/photos/bg7nyt/">http://www.flickr.com/photos/bg7nyt/</a>
        </p>
        <p>Disqus: <a href="http://disqus.com/netkiller/">http://disqus.com/netkiller/</a>
        </p>
        <p>solidot: <a href="http://solidot.org/~netkiller/">http://solidot.org/~netkiller/</a>
        </p>
        <p>pengyou: <a href="http://www.pengyou.com/netkiller">http://www.pengyou.com/netkiller</a>
        </p>
        <p>weibo: <a href="http://weibo.com/bg7nyt">http://weibo.com/bg7nyt</a>
        </p>
        <p>163 Blog: <a href="http://t.163.com/netkiller">http://t.163.com/netkiller</a>
        </p>
        <p><a href="http://groups.google.com/group/netkiller">http://groups.google.com/group/netkiller</a>
        </p>
        <p>Send email to this group: <a href="mailto:netkiller@googlegroups.com">netkiller@googlegroups.com</a>
        </p>
        <p>RSS <a href="http://groups.google.com/group/netkiller/feed/rss_v2_0_topics.xml?num=50">http://groups.google.com/group/netkiller/feed/rss_v2_0_topics.xml?num=50</a>
          <br
          />
        </p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>This is the base Jekyll theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](http://jekyllrb.com/)

You can find the source code for the Jekyll new theme at: [github.com/jglovier/jekyll-new](https://github.com/jglovier/jekyll-new)

You can find the source code for Jekyll at [github.com/jekyll/jekyll](https://github.com/jekyll/jekyll)

