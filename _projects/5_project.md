---
layout: page
title: End-to-End Autonomous Driving AI
description: Isaac Sim, HybridNet, and PPO-based driving policy with a real-time vision observation pipeline.
importance: 5
category: Undergraduate
---

## Project: End-to-End Autonomous Driving AI

> A simulation-based autonomous driving pipeline that combines visual scene understanding with reinforcement learning.

### Background

End-to-end driving policies need compact but informative observations from camera-based perception. This project designed a vision pipeline that converts scene information into reinforcement-learning observations for real-time control.

<div class="text-center my-4">
  <img src="{{ '/assets/img/p7.png' | relative_url }}" alt="NVIDIA Isaac Sim oval track environment" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Fig. 1. Custom oval track environment built in NVIDIA Isaac Sim for end-to-end driving policy training and validation. The track includes lane markings, boundary cones, and a designated start zone for repeatable episode initialization.</em></div>
</div>

### Approach

- Built a HybridNet-based vision pipeline for lane and scene understanding.
- Generated 84-dimensional observation vectors including lane deviation, pixel ratios, and segmentation-mask features.
- Connected NVIDIA Isaac Sim with stable-baselines3 through a TCP socket server-client architecture to resolve dependency conflicts.
- Validated the system against an Oracle agent in simulation.

<div class="text-center my-4">
  <img src="{{ '/assets/img/p7_fig_architecture.png' | relative_url }}" alt="Perception-to-control architecture for Isaac Sim PPO driving" class="img-fluid rounded z-depth-1" style="max-width: 720px; width: 100%; height: auto;">
  <div class="caption"><em>Fig. 2. System architecture of the perception-to-control pipeline. Isaac Sim streams camera frames through a TCP socket server-client interface to resolve dependency conflicts; the HybridNet vision pipeline converts each frame into an 84-dimensional observation vector (lane deviation, pixel ratios, segmentation-mask features) consumed by a stable-baselines3 PPO agent, whose steering and throttle commands return to the simulator. Validation: 2,000+ steps with mean track-center deviation at or below 0.09 m against an Oracle agent.</em></div>
</div>

### Results

- Ran more than 2,000 validation steps in Isaac Sim.
- Maintained average track-center deviation at or below 0.09 m in Oracle-agent validation.
- Established a modular perception-to-control interface for reinforcement-learning experiments.

### Tech Stack

- Python, PyTorch, stable-baselines3
- NVIDIA Isaac Sim, HybridNet
- TCP socket communication
