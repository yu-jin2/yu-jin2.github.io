---
layout: page
title: 종합설계(스마트폰 내 탑재된 센서를 활용한 측위 시스템)
description:
img: assets/img/exp_2.png
importance: 3
category: Undergraduate
---

## 📌 Project: GNSS/INS/SLAM 기반 다중 센서 융합 측위 시스템

> ✔ GNSS 대비 위치 오차 56% 개선 (RMSE 0.57m → 0.25m)  
> ✔ 절대좌표 기반 3D 포인트클라우드 생성 및 안정적 위치 추정 구현
---

### 1. 연구 필요성 (Background)
- 기존 GNSS 및 SLAM 기반 위치 추정은 각각 환경 의존성과 누적 오차 문제 존재
- GNSS는 신호 차단 환경에서 성능 저하, SLAM은 장기 드리프트 발생
- 이를 해결하기 위해 GNSS/INS/SLAM을 결합한 다중 센서 융합 기반 고정밀 측위 시스템 필요

---

### 2. 연구 내용 (Approach)
- 스마트폰 내장 센서(IMU, 카메라, 자이로, 고도계)와 외부 GNSS 수신기를 결합한 측위 시스템 설계
- ORB-SLAM 기반 카메라 궤적 추정 및 3차원 포인트클라우드 생성
- 확장칼만필터(EKF)를 활용한 GNSS/INS/SLAM 센서 융합 알고리즘 구현
- GNSS 데이터를 활용하여 SLAM 지역좌표계를 절대좌표계로 변환
- 다중 센서 데이터 통합을 통한 위치 추정 안정성 및 정밀도 향상

---

### 3. 실험 결과 (Experiment)
- 실제 야외 환경에서 GNSS 단독, GNSS/INS, GNSS/INS/SLAM 성능 비교 실험 수행
- 다양한 이동 경로 및 환경 조건에서 위치 추정 결과 분석
- 센서 조합에 따른 오차 감소 효과 정량적으로 검증

---

### 4. 성과 (Results / Contribution)
- GNSS 단독 대비 RMSE 0.57m → 0.25m로 감소 (약 56% 정확도 향상)
- GNSS 융합을 통해 절대좌표계 기반 3차원 포인트클라우드 생성 가능성 검증
- EKF 기반 다중 센서 융합 알고리즘 설계 및 구현
- SCOPUS 논문 게재(공동 제1저자) 및 교내 우수상 수상

---

### 5. 사용 Tool (Tech Stack)
- Language: C++
- Library: MATLAB, RTKLIB
- System: Ubuntu
- Device: LG V40 Smartphone
- GNSS Receiver: u-blox EVK-M8T, NovAtel ProPak6

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/exp.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/exp_2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/chart_png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>
