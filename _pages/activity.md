---
layout: page
title: Activity
permalink: /activity/
nav: true
nav_order: 3
---

## 교육이수

{% assign edu = site.data.activity | where: "type", "edu" %}
{% for paper in edu %}
<div class="card mt-3">
  <div class="card-body">
    <h5 class="card-title">{{ activiy.title }}</h5>
    <p class="card-text text-muted">{{ activity.event }} &nbsp;|&nbsp; {{ activity.date }}</p>
    <p class="card-text text-muted">{{ activity.discript}}}</p>
  </div>
</div>
{% endfor %}

<br>

## 봉사활동 및 재능기부

{% assign val = site.data.activity | where: "type", "volunteer" %}
{% for paper in val %}
<div class="card mt-3">
  <div class="card-body">
    <h5 class="card-title">{{ activiy.title }}</h5>
    <p class="card-text text-muted">{{ activity.event }} &nbsp;|&nbsp; {{ activity.date }}</p>
    <p class="card-text text-muted">{{ activity.discript}}}</p>
  </div>
</div>
{% endfor %}





