---
layout: page
icon: fas fa-shield-virus
order: 1
title: eCPPTv3
permalink: /ecppt/
---

## Preparación eCPPTv3

Aquí encontrarás todos mis recursos, guías y lecciones aprendidas sobre 
la certificación.

### Artículos destacados
{% assign category = site.categories.eCPPTv3 %}
{% for post in category %}
  - [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%d/%m/%Y" 
}}
{% endfor %}
