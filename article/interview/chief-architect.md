---
layout: post
title: Chief Architect
date: '2016-03-28T10:00:00.000Z'
categories: architect
---

# 架构师

## 瓶颈分析

请分析一下，下面图中可能出现的瓶颈并提出优化方案

User --&gt; Wan -&gt; Firewall -&gt; Switch -&gt; SLB -&gt; Web Server -&gt; Cache -&gt; Database

User -&gt; Nginx -&gt; Tomcat 与 User -&gt; LVS -&gt; Tomcat

## 设计一个10G交换的网络

1. 万兆以太网机房如何规划
2. 防火墙归回
3. 交换机规划
4. 机柜布局规划

