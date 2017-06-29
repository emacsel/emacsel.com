---
layout: default
title: Tags
permalink: /tags
---

<div id="tags">
{% assign tags =  site.episodes
               | map: 'tags'
               | join: ','
               | split: ','
               | uniq 
               | sort %}
{% for tag in tags %}
  <h2>{{ tag }}</h2>
  <ul>
  {% for ep in site.episodes %}
    {% if ep.tags contains tag %}
    <li><a href="{{ site.baseurl }}{{ ep.url }}">{{ ep.title }}</a></li>
    {% endif %}
  {% endfor %}
  </ul>
{% endfor %}
</div>
