---
layout: page
title: Activity
permalink: /activity/
nav: true
nav_order: 3
---

## Training

{% assign edu = site.data.activity | where: "type", "edu" %}
{% for activity in edu %}
<div class="card mt-3">
  <div class="card-body">
    <h5 class="card-title">{{ activity.title }}</h5>
    <p class="card-text text-muted">{{ activity.event }} &nbsp;|&nbsp; {{ activity.date }}</p>
    <p class="card-text text-muted">{{ activity.description }}</p>
  </div>
</div>
{% endfor %}

<br>

## Volunteering & Mentoring

{% assign val = site.data.activity | where: "type", "volunteer" %}
{% for activity in val %}
<div class="card mt-3">
  <div class="card-body">
    <h5 class="card-title">{{ activity.title }}</h5>
    <p class="card-text text-muted">{{ activity.event }} &nbsp;|&nbsp; {{ activity.date }}</p>
    <p class="card-text text-muted">{{ activity.description }}</p>
  </div>
</div>
{% endfor %}
