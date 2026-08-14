---
title: "Projects"
permalink: /projects/
layout: archive
author_profile: true
---

{% for project in site.projects %}
  <div class="archive__item">
    <h2 class="archive__item-title"><a href="{{ project.url }}">{{ project.title }}</a></h2>
    <p>{{ project.excerpt }}</p>
  </div>
{% endfor %}