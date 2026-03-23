---
layout: page
title: 스테레오 카메라와 2D LiDAR 통합 캘리브레이션
description:
img: assets/img/lidar.png
importance: 1
category: Graduate
---

## 📌 Project: Stereo Camera–2D LiDAR 통합 캘리브레이션

> ✔ 1cm 이하 정합 오차 달성  
> ✔ LiDAR intensity 기반 특징 추출
---

### 1. 연구 필요성 (Background)
- 기존 Camera–LiDAR 캘리브레이션은 특징점 매칭 기반으로, LiDAR 데이터의 희소성과 노이즈로 인해 정합 정확도에 한계 존재
- 특히 체스보드 기반 환경에서 LiDAR 특징 추출의 불안정성과 파라미터 추정 오차 문제 발생
- 이를 해결하기 위해 LiDAR intensity 기반 특징 추출과 통합 최적화 기반 캘리브레이션 기법 필요

---

### 2. 연구 내용 (Approach)
- 스테레오 카메라 캘리브레이션 결과로부터 체스보드 3차원 특징점 생성
- 2D LiDAR intensity 데이터를 활용하여 체스보드 격자선 검출 및 교점 추출
- 카메라 3D 특징점과 LiDAR 교점 데이터를 이용한 센서 간 정합 모델 설계
- 최소자승 기반 비선형 최적화(Levenberg-Marquardt)를 통해 외부 파라미터 추정
- Stereo → LiDAR 단계적 구조를 통합 최적화 구조로 확장

---

### 3. 실험 결과 (Experiment)
- 다양한 거리(0.5m ~ 3m) 및 자세 조건에서 실험 수행
- 반복 실험을 통해 캘리브레이션 안정성 검증
- 거리 및 자세 변화에 따른 성능 편차 최소화 확인

---

### 4. 성과 (Results / Contribution)
- 실측 대비 평균 약 1cm 이하 센서 정합 오차 달성
- LiDAR intensity 기반 특징 추출 알고리즘 구현
- Stereo Camera–2D LiDAR 통합 캘리브레이션 구조 설계 및 검증
- 국내 학술대회(항법시스템학회, 2025) 발표

---

### 5. 사용 Tool (Tech Stack)
- Language: C++
- Library: OpenCV
- System: Ubuntu, ROS
- Sensor: FLIR Bumblebee XB3, Hokuyo UTM-30LX

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            loading="eager" 
            path="assets/img/lidar.png" 
            caption="[ 통합 캘리브레이션 시스템 구조도 ]" 
            class="img-fluid rounded z-depth-1" 
        %}
    </div>
</div>
