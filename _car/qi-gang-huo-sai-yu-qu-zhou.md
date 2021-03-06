---
layout: post
title: 气缸活塞与曲轴
date: '2016-05-27T20:00:00.000Z'
categories: jekyll update
---

# 气缸活塞与曲轴

## 气缸活塞与曲轴

5点多醒来，一直睡不着，胡思乱想，终于想出怎么给普通人解释汽车曲轴。

汽车的动力来源于活塞推动连杆，连杆带动曲轴上下\(往复\)运动变成循环\(旋转\)运动。

我用最形象的方式表达，辘轳的工作方式，很多城市的孩纸（子）是没有见过辘轳的。辘轳是一种机械绞盘，古代的起重机械，还是自己百度吧。 如果辘轳的摇臂比较短，手臂伸出去与缩回来的行程比较短，摇起来虽然有点费力，但转速快。 如果摇臂比较长，手臂推出去需要伸直，缩回需要到胸部位置，这样比较省力，但速度就慢了。

有一种辘轳是双摇把的，左右两边各一个摇柄，这种辘轳就是平行曲轴。 如果你还是听不懂，不要急，我用骑自行车（脚踏车）的例子给你讲解，自行车曲柄就是活塞连杆，脚踏板就是活塞，牙盘就是动力输出轴，每次只有一只脚向下踩，两只脚交替踩踏板。

### 汽车曲轴有很多种类，常用的曲轴有平行曲轴跟十字曲轴。

我用音乐知识来解答吧，4/4 拍，一个小节内,音符1,2,3,4完成吸气-压缩-做功-排气这个过程。

```text
|1 2 3 4|1 2 3 4|1 2 3 4|1 2 3 4|
```

音符/数字太多，让我们简化一下，1表示吸气，其他过程省略

```text
|1 - - -|1 - - -|1 - - -|1 - - -|
```

#### 平行曲轴可以理解为两个声部

平行曲轴需要两个气缸相互交替工作.

```text
|吸气-压缩-做功-排气|吸气-压缩-做功-排气|吸气-压缩-做功-排气|吸气-压缩-做功-排气|
|做功-排气-吸气-压缩|做功-排气-吸气-压缩|做功-排气-吸气-压缩|做功-排气-吸气-压缩|

声部1 |1 - - -|1 - - -|1 - - -|1 - - -|
声部2 |- - 2 -|- - 2 -|- - 2 -|- - 2 -|
```

#### 六缸发动机曲轴 120度

V6引擎的曲轴分部是程120夹角，类似三联音，将曲轴平均分成三份，三连音内完成吸气-压缩-做功-排气。

```text
声部1 |1 - -|1 - -|1 - -|1 - -|
声部2 |- 2 -|- 2 -|- 2 -|- 2 -|
声部3 |- - 3|- - 3|- - 3|- - 3|
```

#### 八缸十字曲轴引擎可以理解为四个声部

```text
声部1 |1 - - -|1 - - -|1 - - -|1 - - -|
声部2 |- 2 - -|- 2 - -|- 2 - -|- 2 - -|
声部3 |- - 3 -|- - 3 -|- - 3 -|- - 3 -|
声部4 |- - - 4|- - - 4|- - - 4|- - - 4|
```

#### 如果你还是不懂，\`继续往下看

平行曲轴：

```text
声部1 学习雷锋好榜样，忠于革命忠于党......
声部2 - - 学习雷锋好榜样，忠于革命忠于党......
```

十字曲轴：

```text
声部1 学习雷锋好榜样，忠于革命忠于党......
声部2 - 学习雷锋好榜样，忠于革命忠于党......
声部3 - - 学习雷锋好榜样，忠于革命忠于党......
声部4 - - - 学习雷锋好榜样，忠于革命忠于党......
```

### 气缸与点火顺序

#### 四缸平行曲轴引擎，14一组，23一组，通常用于直列四缸

```text
声部1 |1 - - - |1 - - - |1 - - - |1 - - - |
声部2 |- - 2 - |- - 2 - |- - 2 - |- - 2 - |
声部3 |- - 3 - |- - 3 - |- - 3 - |- - 3 - |
声部4 |4 - - - |4 - - - |4 - - - |4 - - - |
```

上面4缸各缸点火间隔角为180度，点火顺序 1-3-4-2和1-2-4-3

平行曲轴四缸引擎行不行？ 可以，但震动比较大，基本没有厂家采用。

```text
声部1 |1 - - - |1 - - - |1 - - - |1 - - - |
声部2 |- - 2 - |- - 2 - |- - 2 - |- - 2 - |
声部3 |3 - - - |3 - - - |3 - - - |3 - - - |
声部4 |- - 4 - |- - 4 - |- - 4 - |- - 4 - |
```

十字曲轴也可以用于四缸引擎，转速更平顺，常见于小排量四缸摩托车。汽车领域比较少用，震动比较大。

```text
声部1 |1 - - - |1 - - - |1 - - - |1 - - - |
声部2 |- 2 - - |- 2 - - |- 2 - - |- 2 - - |
声部3 |- - 3 - |- - 3 - |- - 3 - |- - 3 - |
声部4 |- - - 4 |- - - 4 |- - - 4 |- - - 4 |
```

#### 直列六缸

直列式6缸发动机的点火顺序是：1－5－3－6－2－4或1－4－2－6－3－5；

```text
声部1 |1 - -|1 - -|1 - -|1 - -|
声部2 |- - 2|- - 2|- - 2|- - 2|
声部3 |- 3 -|- 3 -|- 3 -|- 3 -|
声部4 |- - 4|- - 4|- - 4|- - 4|
声部5 |5 - -|5 - -|5 - -|5 - -|
声部6 |- 6 -|- 6 -|- 6 -|- 6 -|

声部1 |1 - -|1 - -|1 - -|1 - -|
声部2 |- 2 -|- 2 -|- 2 -|- 2 -|
声部3 |- - 3|- - 3|- - 3|- - 3|
声部4 |4 - -|4 - -|4 - -|4 - -|
声部5 |- - 5|- - 5|- - 5|- - 5|
声部6 |- 6 -|- 6 -|- 6 -|- 6 -|
```

#### V6 发动机气缸

```text
左边气缸
声部2 |- 2 -|
声部4 |4 - -|
声部6 |- - 6|

右边气缸
声部1 |1 - -|
声部3 |- - 3|
声部5 |- 5 -|
```

直列式6缸发动机的点火顺序是: 1－4－5－2－3－6

V6 与 L6 区别

直列6缸共用气缸盖，布置一组双顶置的凸轮轴 V6缸相当于两个直列3缸成60度夹角布置的，这样不仅需要两个气缸盖，而且还需要两组凸轮轴。

#### V8,v10,v12,v16,W12 ...

V8发动机有使用平衡曲轴的，也有使用十字曲轴，点火顺序有多种选择。v10,v12,v16,W12... 越来越小众，有兴趣请自行查阅资料

## 总结

平行曲轴两个气缸交替工作，中间存在间歇，出现脉冲式的震动。而六缸将曲轴分为三份120度，三个气缸接力工作，无缝衔接所以相对平顺。 最后V8十字曲轴的将曲轴平均成四份90度。所以平顺性进一步提升。

目前很多配备v8发动机的车型，纷纷改用v6+双涡轮，配备v6引擎的车型也在纷纷改用四缸涡轮增压引擎。

