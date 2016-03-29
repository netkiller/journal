---
layout: page
title: Interview
permalink: /interview/
---

下面是我多年面试总结出来的一些面试题，共享出来供大家参考。

这些试题可以用于人才的快速甄别。我的出发点不是看面试者对技术的掌握程度，而是考研面试者解决问题的能力。

所有试题均采用场景模拟方式进行。

- - -

  <ul class="posts">
    {% for post in site.interview %}
      <li>
        <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>  

- - -

