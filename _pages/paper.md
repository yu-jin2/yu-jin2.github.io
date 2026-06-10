---
layout: page
permalink: /paper/
title: Publications
description: Journal and conference publications.
nav: true
nav_order: 1
---


## Journal

{% assign Journal = site.data.paper | where: "type", "journal" %}
{% for paper in Journal %}
<div class="card mt-3">
  <div class="card-body">
    <h5 class="card-title">{{ paper.title }}</h5>
    <p class="card-text text-muted">{{ paper.event }} &nbsp;|&nbsp; {{ paper.date }}{% if paper.note %} &nbsp;|&nbsp; {{ paper.note }}{% endif %}</p>
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
{% for paper in Conference %}
<div class="card mt-3">
  <div class="card-body">
    <h5 class="card-title">{{ paper.title }}</h5>
    <p class="card-text text-muted">{{ paper.event }} &nbsp;|&nbsp; {{ paper.date }}{% if paper.location %} &nbsp;|&nbsp; {{ paper.location }}{% endif %}{% if paper.note %} &nbsp;|&nbsp; {{ paper.note }}{% endif %}</p>
    <div>
      {% if paper.url %}
      <a href="{{ paper.url }}" target="_blank" class="btn btn-sm btn-outline-secondary">Paper</a>
      {% endif %}
    </div>
  </div>
</div>
{% endfor %}


