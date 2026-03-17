---
layout: page
permalink: /paper/
title: Paper
description: A list of my papers.
nav: true
nav_order: 5
---


## Journal

{% assign Journal = site.data.paper | where: "type", "journal" %}
{% for journal paper %}
<div class="card mt-3">
  <div class="card-body">
    <h5 class="card-title">{{ paper.title }}</h5>
    <p class="card-text text-muted">{{ paper.event }} &nbsp;|&nbsp; {{ paper.date }}</p>
    <div>
      {% if paper.url %}
      <a href="{{ paper.url }}" target="_blank" class="btn btn-sm btn-outline-secondary">Paper</a>
      {% endif %}
    </div>
  </div>
</div>
{% endfor %}

<br>

## Conference

{% assign Conference = site.data.paper | where: "type", "conference" %}
{% for conference paper %}
<div class="card mt-3">
  <div class="card-body">
    <h5 class="card-title">{{ paper.title }}</h5>
    <p class="card-text text-muted">{{ paper.event }} &nbsp;|&nbsp; {{ paper.date }} &nbsp;|&nbsp; {{ paper.location }}</p>
    <div>
      {% if paper.url %}
      <a href="{{ paper.url }}" target="_blank" class="btn btn-sm btn-outline-secondary">Paper</a>
      {% endif %}
    </div>
  </div>
</div>
{% endfor %}


