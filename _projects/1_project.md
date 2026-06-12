---
layout: page
title: Stereo Camera and 2D LiDAR Integrated Extrinsic Calibration
description: Intensity-gradient-based feature extraction and nonlinear least-squares optimization for accurate sensor alignment.
img: assets/img/lidar.png
importance: 1
category: Graduate
---

## Stereo Camera and 2D LiDAR Integrated Extrinsic Calibration

**Intensity-gradient-based feature extraction and nonlinear least-squares optimization for accurate sensor alignment**

<p>
  <span class="badge badge-secondary">C++</span>
  <span class="badge badge-secondary">OpenCV</span>
  <span class="badge badge-secondary">Eigen</span>
  <span class="badge badge-secondary">IEEE Sensors Journal (Under Review)</span>
  <span class="badge badge-secondary">1st Author</span>
</p>

## Overview

This project proposes an integrated calibration method for estimating the extrinsic parameters between a 2D LiDAR and a stereo camera. The method extracts checkerboard boundary features from the reflectance-intensity gradient of the 2D LiDAR, matches them with 3D reconstructed points from the stereo camera, and estimates the extrinsic parameters through nonlinear least-squares optimization. Compared with conventional calibration methods, the proposed method reduced depth-direction alignment error by 90.4%.

## Background & Problem

- A 2D LiDAR provides only a single scan plane, so checkerboard corners cannot be directly extracted and geometric constraints are limited.
- Conventional methods such as LCCT, Vasconcelos, and Khurana assume 3D LiDAR data or sufficient geometric information, which can reduce accuracy in planar-target calibration settings.
- Extrinsic-parameter error contaminates measurements in camera-LiDAR fusion systems and directly affects downstream perception performance.

## Approach

- **Feature extraction:** Detected extrema in the 2D LiDAR reflectance-intensity gradient, defined as delta I / I_avg, to extract checkerboard-grid boundary features.
- **3D correspondence:** Matched LiDAR feature points with 3D points reconstructed from stereo camera calibration.
- **Optimization formulation:** Defined residuals as distances between virtual intersections and actual matched pairs, forming a nonlinear least-squares problem.
- **Numerical optimization:** Implemented Gauss-Newton and Levenberg-Marquardt in C++ with Eigen, and handled conditioning issues through column normalization.
- **Evaluation:** Quantitatively evaluated reprojection error, depth-direction alignment error, and point-cloud alignment visualization.

<div class="text-center my-4">
  <img src="{{ '/assets/img/lidar.png' | relative_url }}" alt="Integrated calibration system structure" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Overall pipeline of the proposed integrated calibration system. The stereo camera provides 3D reference points, while the 2D LiDAR provides intensity-based feature points for joint extrinsic parameter estimation.</em></div>
</div>

## Results

- Conducted repeated experiments over 6 poses and 50 trials at an approximate front-facing distance of 1.5 m.
- Achieved average position error within 1 cm in the forward (+X) and downward (+Z) axes, and within 2 cm in the rightward (+Y) axis.
- Reduced depth-direction alignment error by 90.4% compared with conventional baselines.

<div class="text-center my-4">
  <img src="{{ '/assets/img/fig_bar_errx.png' | relative_url }}" alt="Mean forward-axis error comparison" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Fig. 1. Comparison of mean forward-axis error (Err.X) among the proposed method and three conventional calibration approaches. The proposed method achieves 10.90 mm, corresponding to up to 90.4% error reduction compared with conventional baselines.</em></div>
</div>

<div class="text-center my-4">
  <img src="{{ '/assets/img/fig_line_errx.png' | relative_url }}" alt="Distance-wise forward-axis error comparison" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Fig. 2. Distance-wise forward-axis error (Err.X) comparison across the 2.00-5.75 m evaluation range. The proposed method maintains consistently low error at all target distances.</em></div>
</div>

## Visualization

Before optimization, the reconstructed 3D point cloud, shown with red crosses, shows noticeable structural curvature due to inaccurate initial calibration parameters. After applying the proposed error-state optimization, the point cloud, shown with blue circles, is aligned into a straight plane, demonstrating the algorithm's ability to correct depth-dependent distortions.

<div class="text-center my-4">
  <img src="{{ '/assets/img/fig_top_view.png' | relative_url }}" alt="Top-view point cloud before and after optimization" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Fig. 3. Top-view visualization of reconstructed 3D points before (red crosses) and after (blue circles) the proposed optimization. The optimization corrects depth-dependent structural curvature and recovers accurate metric scale.</em></div>
</div>

## Tech Stack & Publication

**Tech Stack:** C++, OpenCV, Eigen, Gauss-Newton, Levenberg-Marquardt, FlyCapture2, Triclops SDK, urg_library, Bumblebee XB3, Hokuyo UTM-30LX

**Publication:** Yu-Jin Lee, Yu-Dam Lee, Hyung-Keun Lee, "Intensity-Gradient-Based Integrated Calibration of a Stereo Camera and 2D LiDAR Using a Standard Planar Checkerboard," *IEEE Sensors Journal* (SCIE), Under Review, 2026. *(1st Author)*
