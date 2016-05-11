---
layout: page
title: Miscellaneous
permalink: /miscellaneous/
---

乱七八糟没有整理放在这里

- - -

  <ul class="posts">
    {% for post in site.miscellaneous %}
      <li>
        <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>  

- - -

