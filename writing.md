---
layout: default
title: Writing
---

# Writing

## Logic Locking for Chip Security  
A beginner friendly introduction to logic locking.  
👉 [Read the article](https://medium.com/@surabhi.misra30/a-simple-guide-to-logic-locking-for-chip-security-97c5da66b29c)

---

## What Is a Hardware Trojan  
A simple explanation of hardware Trojans written for a general audience.  
👉 [Read the article](https://medium.com/@surabhi.misra30/what-is-a-hardware-trojan-66c8fe66331e)

---

# Writing

Here are my technical guides and posts.

## Long form guide

- **A Technical Guide to Logic Locking for Chip Security**  
  👉 Read the full guide: [Logic Locking Guide](/logic-locking-guide)

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

More posts coming soon.
You can find all posts on my Medium profile:  
[Medium Blog](https://medium.com/@surabhi.misra30)
