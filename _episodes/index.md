---
layout: default
title: Episodes
permalink: /episodes
hide: true
---

{% assign sorted = site.episodes
                 | where_exp: "ep", "ep.hide != true"
                 | sort: 'date'
                 | reverse %}
{% for episode in sorted %}
<article class="index">
    <header>
        <h2 class="index">
            <a href="{{ episode.url }}">{{ episode.title }}</a>
        </h2>
    </header>
</article>
{% endfor %}

