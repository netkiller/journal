---
layout: page
title: Miscellaneous
permalink: /miscellaneous/
---

# miscellaneous

乱七八糟没有整理放在这里

*  {% for post in site.miscellaneous %}
*  {{ post.date \| date: "%b %-d, %Y" }} [{{ post.title }}](https://github.com/netkiller/journal/tree/1f67b9300d493780b7df5c01a6af57e4c24e7b8a/%7B%7B%20post.url%20%7C%20prepend:%20site.baseurl%20%7D%7D)
*  {% endfor %}

