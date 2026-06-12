---
layout: page
title: Lockheed Martin Falcon Challenge
description: YOLOv7 and HSV-based obstacle recognition for drone autonomous flight.
img: assets/img/p6_fig_architecture.png
importance: 7
category: Undergraduate
---

## Project: Lockheed Martin Falcon Challenge

> A hybrid vision-recognition pipeline for autonomous drone flight and obstacle avoidance.

### Background

Autonomous drone missions require reliable object recognition across different distance, lighting, and noise conditions. This project combined deep-learning-based detection with classical image processing to improve mission robustness.

### Approach

- Led algorithm development as team leader.
- Designed a hybrid recognition architecture using YOLOv7 for long-range object detection and HSV-based processing for short-range color recognition.
- Defined switching conditions between recognition modules.
- Connected recognition outputs to path-planning and avoidance-priority control logic.

<div class="text-center my-4">
  <img src="{{ '/assets/img/p6_fig_architecture.png' | relative_url }}" alt="Hybrid YOLOv7 and HSV recognition architecture" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Fig. 1. Hybrid recognition architecture combining YOLOv7 deep-learning detection for long-range objects and HSV color-based recognition for short-range robustness. The switching logic selects the active module based on distance, lighting, and noise conditions, and recognition outputs feed an avoidance-priority control layer.</em></div>
</div>

<div class="text-center my-4">
  <img src="{{ '/assets/img/p6_fig_distance_zones.png' | relative_url }}" alt="Distance-based module assignment concept" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Fig. 2. Distance-based module assignment concept. HSV color recognition provides high frame rates at close range, while YOLOv7 covers distant and small objects with higher detection rates; a switching zone bridges the two operating regions.</em></div>
</div>

### Results

- Reached the semifinals in the Lockheed Martin Falcon Challenge.
- Compared detection rate and FPS across distance, illumination, and noise conditions.
- Implemented a practical vision-to-control interface for autonomous flight missions.

### Tech Stack

- Python, OpenCV, YOLOv7
- HSV color processing
- Autonomous flight mission logic
