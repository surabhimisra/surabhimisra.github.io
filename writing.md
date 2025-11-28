---
layout: default
title: Writing
permalink: /writing/
---

# Writing

All posts from this site on ASIC design, hardware security, and early-career engineering.

---

## All posts

<ul>
{% for post in site.posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span style="font-size: 0.85rem; color: #666;">
      ({{ post.date | date: "%b %-d, %Y" }})
    </span>
  </li>
{% endfor %}
</ul>

---

## More writing

Longer articles on Medium:  
👉 <a href="https://medium.com/@surabhi.misra30" target="_blank">Medium Blog</a>
