---
layout: page
title: Stereo Camera and 2D LiDAR Calibration
description: Integrated calibration using camera-derived 3D features and LiDAR intensity observations.
img: assets/img/lidar.png
importance: 1
category: Graduate
---

## Project: Stereo Camera and 2D LiDAR Calibration

> Integrated extrinsic calibration for sparse 2D LiDAR observations and stereo camera measurements.

### Background

Camera-LiDAR calibration is challenging when LiDAR observations are sparse and noisy. In a checkerboard-based setup, unstable LiDAR feature extraction can directly affect the accuracy of the estimated sensor relationship.

### Approach

- Generated 3D checkerboard features from stereo camera calibration results.
- Extracted checkerboard-related features from 2D LiDAR intensity data.
- Built a sensor alignment model between camera-space 3D features and LiDAR observations.
- Estimated extrinsic parameters using nonlinear least-squares optimization.
- Evaluated calibration stability across distance and pose variations.

### Results

- Implemented an intensity-based LiDAR feature extraction pipeline.
- Designed and verified an integrated stereo camera and 2D LiDAR calibration workflow.
- Achieved sub-centimeter-level alignment error in repeated experimental conditions.
- Presented the work at IPNT Conference 2025.

### Tech Stack

- C++, OpenCV
- Ubuntu, ROS
- FLIR Bumblebee XB3, Hokuyo UTM-30LX

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid loading="eager" path="assets/img/lidar.png" caption="Integrated calibration system structure" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
