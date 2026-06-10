---
layout: page
title: GNSS/INS/SLAM Multi-Sensor Positioning
description: Smartphone and external GNSS receiver integration for more reliable outdoor positioning.
img: assets/img/exp_result_2.png
importance: 3
category: Undergraduate
---

## Project: GNSS/INS/SLAM Multi-Sensor Positioning

> A positioning system that reduced GNSS-only position error by integrating smartphone sensors, SLAM, and an external GNSS receiver.

### Background

GNSS-only positioning can degrade in obstructed outdoor environments, while SLAM can suffer from drift over time. This project combined GNSS, INS, and SLAM data to improve positioning stability.

### Approach

- Combined smartphone sensors, camera-based SLAM, altitude information, and external GNSS receiver data.
- Used ORB-SLAM for visual tracking and 3D point-cloud generation.
- Implemented an EKF-based sensor fusion process.
- Converted SLAM estimates into a global coordinate frame using GNSS observations.
- Compared GNSS-only, GNSS/INS, and GNSS/INS/SLAM performance.

### Results

- Reduced position RMSE from 0.57 m to 0.25 m compared with GNSS-only positioning.
- Verified 3D point-cloud generation in a global coordinate frame.
- Demonstrated improved positioning stability through multi-sensor fusion.
- Published related work in a SCOPUS/KCI journal and received a domestic undergraduate paper award.

### Tech Stack

- C++, MATLAB, RTKLIB
- Ubuntu
- LG V40 smartphone, u-blox EVK-M8T, NovAtel ProPak6

<div class="row">
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid loading="eager" path="assets/img/exp_r.jpg" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Experiment environment</div>
  </div>
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid loading="eager" path="assets/img/exp_result_2.png" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Point cloud and trajectory result</div>
  </div>
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid loading="eager" path="assets/img/chart.jpg" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Performance comparison</div>
  </div>
</div>
