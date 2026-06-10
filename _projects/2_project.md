---
layout: page
title: Stereo Camera Calibration Accuracy Comparison
description: Calibration accuracy analysis under limited image data and varying capture conditions.
img: assets/img/stereo_ov.jpg
importance: 2
category: Graduate
---

## Project: Stereo Camera Calibration Accuracy Comparison

> A stereo calibration study focused on robust parameter estimation with limited image data.

### Background

Conventional stereo calibration can accumulate error when intrinsic and extrinsic parameters are estimated separately or when only a small number of calibration images is available. This project compared calibration performance under constrained data conditions.

### Approach

- Built a C++ image acquisition and processing pipeline for the FLIR Bumblebee XB3 stereo camera.
- Extracted checkerboard corner features from 9 x 6 calibration patterns.
- Designed an optimization process that estimates camera parameters using 3D feature geometry.
- Compared calibration performance across different image counts and capture conditions.

### Results

- Achieved an average calibration RMSE below 0.6 px in full-data experiments.
- Maintained stable calibration behavior even with limited image sets.
- Estimated focal length and baseline parameters with low relative error.
- Presented the work at the Korean Society for Aeronautical and Space Sciences Conference 2025.

### Tech Stack

- C++, OpenCV, FlyCap2
- FLIR Bumblebee XB3

<div class="row">
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid path="assets/img/stereo_ov.jpg" class="img-fluid rounded z-depth-1" %}
    <div class="caption">System overview</div>
  </div>
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid path="assets/img/sensor.jpg" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Sensor setup</div>
  </div>
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid path="assets/img/stereo_result.png" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Experiment result</div>
  </div>
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid path="assets/img/stereo_ov_detail.png" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Calibration detail</div>
  </div>
</div>
