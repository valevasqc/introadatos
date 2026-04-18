---
layout: default
title: Introducción a Datos
---

# Introducción a Datos

Laboratorios trabajados en el curso:

{% assign notebooks = site.static_files | where_exp: "file", "file.extname == '.ipynb'" | sort: "name" %}
{% assign root_count = 0 %}
{% for nb in notebooks %}
{% assign path_parts = nb.path | split: '/' %}
{% if path_parts.size == 2 %}
{% assign root_count = root_count | plus: 1 %}
- [{{ nb.name }}]({{ nb.path | relative_url }})
{% endif %}
{% endfor %}
{% if root_count == 0 %}
Aún no hay notebooks en la raíz del repositorio.
{% endif %}
