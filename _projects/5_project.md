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

### Approach

- Built a HybridNet-based vision pipeline for lane and scene understanding.
- Generated 84-dimensional observation vectors including lane deviation, pixel ratios, and segmentation-mask features.
- Connected NVIDIA Isaac Sim with stable-baselines3 through a TCP socket server-client architecture to resolve dependency conflicts.
- Validated the system against an Oracle agent in simulation.

### Results

- Ran more than 2,000 validation steps in Isaac Sim.
- Maintained average track-center deviation at or below 0.09 m in Oracle-agent validation.
- Established a modular perception-to-control interface for reinforcement-learning experiments.

### Tech Stack

- Python, PyTorch, stable-baselines3
- NVIDIA Isaac Sim, HybridNet
- TCP socket communication
