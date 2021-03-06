---
layout: post
title: software architect
date: '2016-03-28T10:00:00.000Z'
categories: software architect
---

# software-architect

### 软件架构师

### WEB 应用

#### 动态与静态分离

1. 谈谈怎样分离动态音静态内容
2. SSI 服务器端包含应用

### 数据库应用

#### 数据库分割问题

1. 什么是顺平分割，什么是垂直分割
2. 分表，分库有需要主要那些事项
3. 分表，分库后怎么解决夸库查询
4. 分表，分库后怎么创建索引

#### 数据库复制问题

1. 数据库复制有哪几种？
2. 简述主从复制，主主复制，环形复制
3. 当选择主从复制是软件开发上有哪些注意事项
4. 主主如何应用

## 软件弹性设计

#### 编译语言的弹性设计问题

背景模拟： 有一个电商平台已经开发完毕，编译打包，上线，运营。 由于市场瞬息万变，原有的打折系统设计已经不能满足现在的需求，如果不修改可会会给公司带来经济随时。 现在需要重新修改程序逻辑，但问题来了。目前正在做推广促销活动，系统访问量大不能中断现有服务，哪怕30都会给公司带来不可挽回的损失。

我的问题： 1. 怎样在这个系统的设计之初解决后面遇到的问题 2. 如何设计一个弹性打折系统 3. 在不重启的情况下怎样改编编译语言的内部运行逻辑

问题延伸： 这个问题可以延伸到苹果IOS，例如发布app到苹果appstore至少需要半个月，半个月可能存在很多变数，很可能应用被审批通过，程序已经不在适合当前的情况了。

### 高可用设计

1. 什么是高可用
2. 什么是双机热备，双机热备有那些缺陷
3. 什么是双活
4. 请简述实现软件高可用要考虑那些因素

#### 软件设计中的灾备问题

请简述设计一个远程异地灾备系统

1. 两个机房怎样设计灾备系统
2. 三个机房怎样设计灾备系统
3. 跨境情况需要考虑那些影响因素

#### 软件灾备开发问题

1. 数据库怎样实现灾备
2. 缓存怎样实现灾备
3. 应用服务器怎样实现灾备
4. Web 服务器怎样实现灾备
5. 计划任务、定时周期运行的程序怎样灾备
6. 消息队列怎样实现灾备
7. 双活的软件怎样实现同一时刻只能一个运行，或者交替运行

### 软件部署问题

1. 怎样实现软件自动化部署，实现自动化部署的关键几点是什么？
2. 怎样处理配置文件
3. 怎样排除不必要或者不希望部署的文件
4. 怎样实现增量部署
5. 怎样实现差异部署
6. 怎样部署大文件，例如视频等。问题：有一个文件有500M，内容随时有修改，也会不定期追加，怎样实现差异部署，而不是再次发布一个500M的文件。
7. 怎样部署编译软件
8. 怎样备份
9. 怎样部署windows程序
10. 怎样快速回撤，切换时间点或者指定的版本。

以上不允许使用GIT/SVN实现自动部署。要求自动化不是在30秒内完成。

## 软件开发框架

#### 插件的实现原理

1. 插件有几部分组成
2. 如何实现插件安装，卸载，启用，禁用？
3. 安装，卸载，启用，禁用怎样实现不停机，不关闭服务的情况进行？

#### 口述如何设计一个MVC框架

1. 怎样实现 URL 路由
2. 怎样实现控制器
3. 怎样实现视图
4. 怎样实现模型

#### 口述如何设计一个SOA框架

1. 框架分为几个部分？
2. 采用什么协议与框架通信？
3. 如果考虑到性能使用二进制协议你怎样实现？
4. 如何解决并发冲突?
5. 如何支持事务?
6. 你怎样与消息队列集成或者通信？

#### 口述设计一个分布式计划任务系统

背景：计划任务即周期或定时运行的程序，我们要解决单点故障问题与负载均衡的问题，在一个分布式系统中单节点是不允许的。

设计要求：能够实现高可用，负载均衡，横向扩展

1. 怎样处理同时运行产生的冲突问题？
2. 怎样排队运行？
3. 任务如何持久化？
4. 一个节点宕机，另一个节点怎么接管没有完成的任务？
5. 如何横向扩展？
6. 扩展，收缩，维护如果能做到不停机，不影响业务？

### 分布式开发

1. 怎样解决分布式节点的延迟问题,例如A节点保存数据，B节点查询不到

