---
tab: none
title: Bitácora
layout: page
---

Esta bitácora contiene los siguientes comentarios:

{% assign default_paths = site.pages | map: "path" %}
{% assign page_paths = site.header_pages | default: default_paths %}

{% if page_paths %}
  {% for path in page_paths %}
    {% assign my_page = site.pages | where: "path", path | first %}
    {% if my_page.tab == "none" %}
        {% if my_page.title != "Nada" %}
            {% if my_page.path != "index.md" %}
* [{{ my_page.label | default: my_page.title }}]({{ my_page.url | relative_url }})
            {% endif %}
        {% endif %}
    {% endif %}
  {% endfor %}
{% endif %}
