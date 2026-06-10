---
layout: about
title: about
permalink: /
subtitle: Multi-sensor calibration and 3D vision engineer focused on reliable positioning systems.

profile:
  align: right
  image: profile_jin.jpg
  image_circular: false
  more_info: >
    <p>M.S., Korea Aerospace University, expected Feb. 2026</p>
    <p>B.S., Korea Aerospace University, Aug. 2024</p>

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

**Tools:** C++, Python, MATLAB, OpenCV, ROS, RTKLIB, CATIA

<br>

## Research Highlight

- Submitted a first-author paper to **IEEE Sensors Journal (SCIE)**: *Intensity-Gradient-Based Integrated Calibration of a Stereo Camera and 2D LiDAR Using a Standard Planar Checkerboard*.
- Achieved a **90.4% reduction in depth-direction alignment error** through intensity-gradient feature extraction and nonlinear least-squares optimization.
- Implemented Gauss-Newton and Levenberg-Marquardt optimization in C++ with Eigen, including Jacobian derivation and numerical conditioning.

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
