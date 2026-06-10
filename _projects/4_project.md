---
layout: page
title: Velodyne VLP-16 Voxel Analysis Pipeline
description: Raw UDP packet parsing, accumulated voxel analysis, and RANSAC road-plane detection.
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

### Results

- Built a ROS-independent C++ parsing and analysis pipeline.
- Improved road-plane RANSAC inlier ratio from 22% to 77%.
- Produced voxel-level features for downstream perception and calibration analysis.

### Tech Stack

- C++, Python
- Velodyne VLP-16, KITTI dataset
- Voxel analysis, RANSAC
