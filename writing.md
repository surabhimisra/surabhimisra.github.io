---
layout: default
title: Writing
---

# Writing

This page collects my articles, guides, and posts related to ASIC design, hardware security, and early career engineering.

---

## Featured Articles (Medium)

### Logic Locking for Chip Security  
A beginner friendly introduction to logic locking.  
👉 <a href="https://medium.com/@surabhi.misra30/a-simple-guide-to-logic-locking-for-chip-security-97c5da66b29c" target="_blank">Read the article</a>

### What Is a Hardware Trojan  
A simple explanation of hardware Trojans written for a general audience.  
👉 <a href="https://medium.com/@surabhi.misra30/what-is-a-hardware-trojan-66c8fe66331e" target="_blank">Read the article</a>

---

## Long Form Guides (This Site)

### A Technical Guide to Logic Locking for Chip Security  
A longer, more detailed guide with examples.  
👉 <a href="/logic-locking-guide" style="text-decoration: underline;">Read the full guide</a>

---

## All Blog Posts (This Site)

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

More posts coming soon.

---

## More Writing  
You can find all of my Medium posts here:  
👉 <a href="https://medium.com/@surabhi.misra30" target="_blank">Medium Blog</a>
