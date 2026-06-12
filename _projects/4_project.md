---
layout: page
title: Velodyne VLP-16 Voxel Analysis Pipeline
description: Raw UDP packet parsing, accumulated voxel analysis, and RANSAC road-plane detection.
img: assets/img/p4_fig_ransac.png
importance: 4
category: Graduate
---

## Project: Velodyne VLP-16 Voxel Analysis Pipeline

> A ROS-independent point-cloud processing pipeline for automotive LiDAR data.

### Background

Automotive perception research often relies on middleware abstractions, but raw LiDAR packet handling is useful for understanding the full sensor pipeline. This project processed Velodyne VLP-16 packets directly and analyzed accumulated urban point clouds.

### Approach

- Parsed 1206-byte UDP packets directly, including 12 firing blocks and 16 channels.
- Processed 433 accumulated frames from the KITTI urban driving dataset.
- Extracted voxel attributes including occupancy, mean reflectance, point density, and height variance.
- Applied Z-layer reliable-voxel filtering before RANSAC road-plane detection.

<div class="text-center my-4">
  <img src="{{ '/assets/img/p4_fig_pipeline.png' | relative_url }}" alt="Velodyne VLP-16 voxel analysis pipeline" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Fig. 1. Overall processing pipeline: raw 1206-byte UDP packets are parsed without ROS dependency, accumulated over 433 KITTI frames, voxelized with per-voxel attributes, and filtered by Z-layer reliability before RANSAC road-plane detection.</em></div>
</div>

### Results

- Built a ROS-independent C++ parsing and analysis pipeline.
- Improved road-plane RANSAC inlier ratio from 22% to 77%.
- Produced voxel-level features for downstream perception and calibration analysis.

<div class="text-center my-4">
  <img src="{{ '/assets/img/p4_fig_ransac.png' | relative_url }}" alt="Road-plane RANSAC inlier ratio improvement" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Fig. 2. Road-plane RANSAC inlier ratio before and after reliable-voxel filtering. Restricting RANSAC input to Z-layer-filtered reliable voxels improves the inlier ratio from 22% to 77%.</em></div>
</div>

### Tech Stack

- C++, Python
- Velodyne VLP-16, KITTI dataset
- Voxel analysis, RANSAC
