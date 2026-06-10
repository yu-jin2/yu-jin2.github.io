---
layout: page
title: LSTM-Based Multi-Robot Dispatch Optimization
description: Time-series prediction and batch dispatch for a simulated multi-robot serving system.
img: assets/img/lstm_1.jpg
importance: 5
category: Undergraduate
---

## Project: LSTM-Based Multi-Robot Dispatch Optimization

> LSTM-based time prediction improved cook-time prediction error and reduced average waiting time in a multi-robot dispatch simulation.

### Background

Conventional dispatch systems often rely on the current state only, which makes them less responsive to time-dependent order patterns. Food preparation and serving workflows also have sequential dependencies that are well suited to time-series modeling.

### Approach

- Designed a simulated multi-serving-robot environment.
- Generated time-series data reflecting order flow, table demand, and repeated menu patterns.
- Built LSTM prediction models for cook time and meal time.
- Compared LSTM prediction against a linear-regression baseline.
- Designed a batch-serving dispatch algorithm using predicted completion times.

### Results

- Reduced cook-time prediction MAE by approximately 33%.
- Reduced average waiting time by approximately 39% in the dispatch simulation.
- Verified that time-series prediction can improve practical robot dispatch efficiency.

### Tech Stack

- Python, TensorFlow, scikit-learn, pandas, NumPy, Matplotlib
- Google Colab
- LSTM, linear regression, greedy dispatch optimization

<div class="row">
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid loading="eager" path="assets/img/lstm_2.jpg" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Multi-robot dispatch comparison</div>
  </div>
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid loading="eager" path="assets/img/lstm_1.jpg" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Waiting-time distribution after optimization</div>
  </div>
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid loading="eager" path="assets/img/lstm_3.jpg" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Prediction accuracy comparison</div>
  </div>
</div>
