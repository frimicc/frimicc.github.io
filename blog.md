---
layout: page
title: Articles
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      &nbsp; <span class="article-date">{{ post.date | date: '%B %d, %Y' }}</span>
    </li>
  {% endfor %}
</ul>
