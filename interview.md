---
layout: page
title: Interview
permalink: /interview/
---

# interview

下面是我多年面试总结出来的一些面试题，共享出来供大家参考。

这些试题可以用于人才的快速甄别。我的出发点不是看面试者对技术的掌握程度，而是考研面试者解决问题的能力。

所有试题均采用场景模拟方式进行。

*  {% for post in site.interview %}
*  {{ post.date \| date: "%b %-d, %Y" }} [{{ post.title }}](https://github.com/netkiller/journal/tree/1f67b9300d493780b7df5c01a6af57e4c24e7b8a/%7B%7B%20post.url%20%7C%20prepend:%20site.baseurl%20%7D%7D)
*  {% endfor %}

