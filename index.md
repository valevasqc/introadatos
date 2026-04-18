---
layout: default
title: Inicio
---

# Introducción a Datos

Este sitio muestra mis notebooks del curso.

## Notebooks

{% assign notebooks = site.static_files | where_exp: "file", "file.extname == '.ipynb'" | sort: "name" %}
{% if notebooks.size > 0 %}
{% for nb in notebooks %}
- [{{ nb.name }}]({{ nb.path | relative_url }})
{% endfor %}
{% else %}
Aún no hay notebooks en la raíz del repositorio.
{% endif %}

> Se listan automáticamente los archivos `.ipynb` que estén en la raíz del repo.
