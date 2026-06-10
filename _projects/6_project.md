---
layout: page
title: GPS-Denied UGV Path Planning with Uncertainty Map
description: A* warm start and Levenberg-Marquardt trajectory optimization under GPS-denied conditions.
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

### Results

- Produced GPS-denied navigation trajectories using uncertainty-aware planning.
- Combined search-based initialization with nonlinear trajectory refinement.
- Connected dataset-driven map information to robot simulation validation.

### Tech Stack

- C++, Eigen
- ROS2, Gazebo, TurtleBot3
- KAIST Complex Urban Dataset
