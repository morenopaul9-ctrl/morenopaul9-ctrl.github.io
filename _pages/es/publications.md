---
layout: archive
title: "Publicaciones"
permalink: /es/publicaciones/
author_profile: true
---

Mi trabajo académico comprende investigaciones en economía política internacional y política comparada, así como contribuciones a la divulgación histórica. Esta página reúne artículos de investigación, tesis académicas y trabajos de historia y divulgación.

{% include base_path %}

{% assign categories_es = "articles,Artículos de investigación|history,Historia y divulgación|theses,Tesis y disertaciones" | split: "|" %}

{% for category_entry in categories_es %}
  {% assign category_parts = category_entry | split: "," %}
  {% assign category_key = category_parts[0] %}
  {% assign category_title = category_parts[1] %}
  {% assign title_shown = false %}

  {% for post in site.publications reversed %}
    {% if post.category != category_key %}
      {% continue %}
    {% endif %}

    {% unless title_shown %}
<h2>{{ category_title }}</h2>
<hr />
      {% assign title_shown = true %}
    {% endunless %}

    {% include archive-single.html %}
  {% endfor %}
{% endfor %}
