---
layout: page
title: GPS-Denied UGV Path Planning with Uncertainty Map
description: A* warm start and Levenberg-Marquardt trajectory optimization under GPS-denied conditions.
img: assets/img/p5_fig_tradeoff.png
importance: 6
category: Graduate
---

## Project: GPS-Denied UGV Path Planning with Uncertainty Map

> A C++ path-planning pipeline that uses uncertainty maps to support navigation when GPS quality degrades.

### Background

Urban navigation can become unreliable when GPS is degraded or unavailable. This project used LiDAR and GPS-quality cues to construct uncertainty maps and plan trajectories in simulation.

### Approach

- Implemented A* warm-start path generation in C++.
- Built a Levenberg-Marquardt trajectory optimizer with Eigen.
- Constructed uncertainty maps from LiDAR intensity and GPS-quality metrics such as HDOP and satellite count.
- Validated the planner with TurtleBot3 in ROS2 Gazebo using the KAIST Complex Urban Dataset.

<div class="text-center my-4">
  <img src="{{ '/assets/img/p5_fig_pipeline.png' | relative_url }}" alt="GPS-denied UGV path planning pipeline" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Fig. 1. Overall pipeline: LiDAR intensity and GPS-quality metrics (HDOP, satellite count) construct an uncertainty map, an A* warm-start path is generated in C++, and the trajectory is refined by Levenberg-Marquardt optimization with four cost functions, validated on TurtleBot3 in ROS2 Gazebo using the KAIST Complex Urban Dataset.</em></div>
</div>

### Results

- Produced GPS-denied navigation trajectories using uncertainty-aware planning.
- Combined search-based initialization with nonlinear trajectory refinement.
- Connected dataset-driven map information to robot simulation validation.
- Used w_unc = 1.5 as a balanced operating point, limiting path-length increase to 1.4% while reducing accumulated uncertainty.
- Used the 40% initial-value success rate as the baseline motivation for adding an A* warm-start before nonlinear trajectory optimization.

<div class="text-center my-4">
  <img src="{{ '/assets/img/p5_fig_tradeoff.png' | relative_url }}" alt="Path length and uncertainty trade-off" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Fig. 2. Trade-off between path length increase and accumulated uncertainty as a function of the uncertainty weight. At w_unc = 1.5, the planner reaches a balanced operating point with only 1.4% path length increase while substantially reducing uncertainty accumulation.</em></div>
</div>

### Tech Stack

- C++, Eigen
- ROS2, Gazebo, TurtleBot3
- KAIST Complex Urban Dataset
