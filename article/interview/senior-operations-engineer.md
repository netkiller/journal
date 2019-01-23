---
layout: post
title: 'senior operations engineer '
date: '2016-03-03T10:00:00.000Z'
categories: engineer operations
---

# 高级运维工程师

## 服务器硬件

### RAID 磁盘阵列

1. 简述 RAID？
2. RAID 0 5 6 10 50 都适用于那些场景？
3. 数据库适用那种 RAID？
4. RAID 10 磁盘结构是怎样的，RAID 10 可以允许损坏那几块硬盘，请指出那就几块可以损坏，那几块不能损坏？
5. 什么是逻辑卷，适合那些场景？

`磁盘阵列`

```text

+------+------+------+
| HDD1 | HDD3 | HDD5 |
+------+------+------+
| HDD2 | HDD4 | HDD6 | 
+------+------+------+
```

### 存储

1. 谈谈 iSCSI 与 SAN
2. 两个电脑挂载同一个 iSCSI 设备，是否可行？

### 磁盘 IO

1. 服务器IO瓶颈都在那些地方？

### Fibre Channel vs FCoE

1. 请比较 Fibre 与 FCoE 有缺点，以及适合场景

## 网络

1. 由于网卡损坏，或者水晶头接触不良导致断线，有没有解决方案？
2. 当网卡1G已经不能满足通信要求，你怎么样应对，你的解决方案是什么？

## DNS

1. 简述如何将DNS服务从万网迁移至DnsPod，需要注意哪些事项？
2. 什么是A记录，CNAME记录，TXT记录，MX记录，NS记录？
3. 怎样查看域名的过期时间？
4. 怎样配置SPF，DKIM？

## Linux 操作系统

一个全新的 Linux 服务器，你会做哪些初始化操作？

RPM安装 与 编译安装有什么区别，是否编译安装性能会更好？

## 文件系统

1. 简述 fdisk 与 gpt
2. 文件系统怎样做快照，怎样快速恢复快照
3. 文件系统损坏怎么修复
4. 怎样查看磁盘的UUID

## 进程管理

1. 怎么样查看某一个文件正在被那个程序访问?

## Web 服务器

1. 怎样实现防盗链？
2. 怎样屏蔽爬虫？
3. 怎样防止注入攻击？
4. 注入都有哪些手段？
5. WEB 服务器安全配置都有哪些？
6. 怎样保证 WEB 服务目录/文件的安全?
7. 怎样防止文件被修改？
8. 怎样第一时间发现文件被撰改？并提前拦截？

## 应用服务器

1. 谈谈Tomcat优化
2. Nginx 通过代理服务器访问 Tomcat ， Java应用输出页面含有SSI标签，Nginx 怎样处理 java 输出的SSI标签

## Nginx location 基础知识？

当前 document root 是 /www/example.com/www.example.com URL 为 [http://www.example.com](http://www.example.com)

现在需要实现 [http://www.example.com/inc](http://www.example.com/inc)

将 inc 定为到 /www/example.com/inc.example.com

请问如何实现

## 下面两个配置的结果是什么

```text
    location /test/ {
        root /www/netkiller.cn/live.netkiller.cn/public;
    }
```

```text
    location ^~ /test/ {
        root /www/netkiller.cn/live.netkiller.cn/public;
    }
```

## Proxy 两个配置的结果是什么

```text
    location ^~ /test/ {
        ssi on;
        proxy_set_header Accept-Encoding "";
        proxy_pass http://www.netkiller.cn;
        proxy_set_header Host www.netkiller.cn;
        proxy_cache www;
        proxy_cache_valid  200 302  1m;
    }
```

```text
    location ^~ /test/ {
        ssi on;
        proxy_set_header Accept-Encoding "";
        proxy_pass http://www.netkiller.cn/;
        proxy_set_header Host www.netkiller.cn;
        proxy_cache www;
        proxy_cache_valid  200 302  1m;
    }
```

## Rewrite

源地址： [http://www.netkiller.cn/index.html?id=100](http://www.netkiller.cn/index.html?id=100)

Rewrite后： [http://www.netkiller.cn/article/100.html](http://www.netkiller.cn/article/100.html)

请问如何实现

## X-Forward-For

1. x-forward-for 原理是什么？
2. IP 地址存储的顺序？

## Mail 服务器

1. 什么事别名
2. 什么是虚拟域
3. 怎样防垃圾邮件
4. 怎么实现 SMTP 认证，SMTP加密算法有那几种
5. 怎样配置 SSL SMTP/POP/IMAP
6. 自建EDM（电子邮件推广）服务器需要哪些条件？注意事项？怎样避免被封锁。
7. 邮件怎样转寄
8. 怎样配置邮件列表服务器
9. 怎样配置SPF，DKIM？

## 攻击防守

1. 如果被挂马怎么除了？
2. 被植入代码有哪些特点，怎样快速找到被植入的木马。
3. 怎样监控恶意代码入住或修改
4. 什么是UDP流量攻击，怎样防止UDP流量攻击？
5. 怎样防止恶意穷举邮箱密码
6. 怎样防止穷举SSH密码

## 服务器监控

1. 服务器监控都有哪些手段？
2. 网络设备都有哪些监控手段？
3. 监控除了SNMP还有那些协议？
4. 怎样监控硬件，例如硬盘损坏？服务器风扇停转？

