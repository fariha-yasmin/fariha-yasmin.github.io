---
title: "Notes"
permalink: /notes/
layout: archive
author_profile: true
---

Reference notes from my studies and research — theory, methods, and practical workflows. I write them to understand things properly, and keep them here so they stay searchable.

{% assign note_groups = site.notes | group_by: "category" %}
{% for group in note_groups %}
<h2 class="archive__subtitle">{{ group.name }}</h2>
{% for note in group.items %}
  <div class="archive__item">
    <h2 class="archive__item-title"><a href="{{ note.url }}" rel="permalink">{{ note.title }}</a></h2>
    <p class="archive__item-excerpt">{{ note.excerpt }}</p>
  </div>
{% endfor %}
{% endfor %}
