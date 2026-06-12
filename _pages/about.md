---
layout: about
title: about
permalink: /
subtitle: Multi-sensor calibration and 3D vision engineer working on sensor fusion and perception for autonomous systems.

profile:
  align: right
  image: profile_jin.jpg
  image_circular: false

selected_papers: false
social: false

announcements:
  enabled: false
  scrollable: true
  limit: 5

latest_posts:
  enabled: false
  scrollable: true
  limit: 3
---

I design and validate positioning and perception systems that combine cameras, LiDAR, GNSS, INS, and SLAM. My work spans the full pipeline: sensor setup, data acquisition, feature extraction, mathematical modeling, optimization, and experimental verification.

My current research focuses on high-precision calibration between stereo cameras and 2D LiDAR. I build calibration procedures around real sensor behavior, including sparse LiDAR observations, intensity-gradient-based feature extraction, and nonlinear optimization for extrinsic parameter estimation.

I also have experience with GNSS/INS/SLAM sensor fusion for positioning in dynamic outdoor environments. Through undergraduate and graduate projects, I have implemented systems that improve positioning reliability, generate 3D point clouds, and evaluate performance against baseline GNSS-only approaches.

**Research interests:** multi-sensor fusion, camera-LiDAR calibration, 3D vision, GNSS/SLAM positioning, robotics perception

**Tools:** C++, Python, MATLAB, OpenCV, ROS, ROS2, RTKLIB, CATIA

<div style="clear: both;"></div>

<br>

## Current & Education

- Research Engineer, Aviation Electronics Research Institute, KAU (Mar. 2026-)
- M.S., Korea Aerospace University, Feb. 2026 (GPA 4.50/4.50)
- B.S., Korea Aerospace University, Aug. 2024 (GPA 4.02/4.50)

<br>

## Research Highlight

- Submitted a first-author paper to **IEEE Sensors Journal (SCIE)**: *Intensity-Gradient-Based Integrated Calibration of a Stereo Camera and 2D LiDAR Using a Standard Planar Checkerboard*.
- Achieved a **90.4% reduction in depth-direction alignment error** through intensity-gradient feature extraction and nonlinear least-squares optimization.
- Co-first-authored a SCOPUS-indexed paper on GNSS/INS/SLAM fusion positioning, improving RMSE by 56% (0.571 m to 0.251 m) with a 15-state error-state EKF.

<br>

## Awards

- Best Paper Award, IPNT Spring Conference 2026 (1st author) - Integrated calibration of 2D LiDAR and stereo camera
- Best Paper Award, IPNT Conference 2024 (co-author) - SDR-based GNSS and LEO satellite navigation
- Capstone Design Excellence Award, Korea Aerospace University, 2024

<br>

## Selected Papers

{% assign spaper = site.data.paper | where: "selected", true %}
{% for paper in spaper %}
<div class="card mt-3">
  <div class="card-body">
    <h5 class="card-title">{{ paper.title }}</h5>
    <p class="card-text text-muted">{{ paper.event }} &nbsp;|&nbsp; {{ paper.date }}{% if paper.location %} &nbsp;|&nbsp; {{ paper.location }}{% endif %}{% if paper.note %} &nbsp;|&nbsp; {{ paper.note }}{% endif %}</p>
    <div>
      {% if paper.url %}
      <a href="{{ paper.url }}" target="_blank" class="btn btn-sm btn-outline-secondary">Paper</a>
      {% endif %}
    </div>
  </div>
</div>
{% endfor %}
