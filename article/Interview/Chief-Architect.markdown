---
layout: post
title:  "Chief Architect"
date:   2016-03-28 10:00:00
categories: architect
---

架构师
-----

### 瓶颈分析

请分析一下，下面图中可能出现的瓶颈并提出优化方案

User --> Wan -> Firewall -> Switch -> SLB -> Web Server -> Cache -> Database

User -> Nginx -> Tomcat 
与 
User -> LVS -> Tomcat 

### 设计一个10G交换的网络

1. 万兆以太网机房如何规划
1. 防火墙归回
1. 交换机规划
1. 机柜布局规划

- - -