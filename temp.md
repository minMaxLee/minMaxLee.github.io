---
layout: page
title: Debug Categories
permalink: /debug-cats/
---

{% for cat in site.categories %}
- **{{ cat[0] }}** — {{ cat[1].size }} posts
{% endfor %}
