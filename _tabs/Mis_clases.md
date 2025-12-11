---
layout: page
icon: fas fa-chalkboard-teacher
order: 3
title: Clases Ciber
permalink: /clases/
---

## Mis Clases y Formaciones

Recopilación de las sesiones que he impartido.

{% assign category = site.categories.Clases %}
{% for post in category %}
  - [{{ post.title }}]({{ post.url }})
{% endfor %}
