---
layout: default
title: "Blog"
permalink: /blog/
---

# Blog

Welcome to my writing! I post about ASIC design, hardware security, Trojans, logic locking,
and my research experiments.

## Posts

<ul>
{% for post in site.posts %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <span style="color:#777; font-size:0.85rem;"> — {{ post.date | date: "%B %d, %Y" }}</span>
  </li>
{% endfor %}
</ul>
