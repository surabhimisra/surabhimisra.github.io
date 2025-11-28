---
layout: default
title: Writing
---

# Writing

A collection of my articles and notes on ASIC design, hardware security, and early-career engineering.

---

## Latest Posts

<ul>
{% for post in site.posts limit:3 %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span style="font-size: 0.85rem; color: #666;">
      ({{ post.date | date: "%b %-d, %Y" }})
    </span>
  </li>
{% endfor %}
</ul>

---

## Featured on Medium

**Logic Locking for Chip Security**  
👉 <a href="https://medium.com/@surabhi.misra30/a-simple-guide-to-logic-locking-for-chip-security-97c5da66b29c" target="_blank">Read on Medium</a>

**What Is a Hardware Trojan?**  
👉 <a href="https://medium.com/@surabhi.misra30/what-is-a-hardware-trojan-66c8fe66331e" target="_blank">Read on Medium</a>

---

## Guides on This Site

**A Technical Guide to Logic Locking**  
👉 <a href="/logic-locking-guide" target="_blank">Read the guide</a>

**Research Paper Summaries**  
👉 <a href="/paper-summaries/" target="_blank">View summaries</a>

---

## More Writing

All Medium articles:  
👉 <a href="https://medium.com/@surabhi.misra30" target="_blank">Medium Blog</a>
