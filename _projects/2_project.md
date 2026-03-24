---
layout: page
title: 스테레오 카메라 캘리브레이션
description:
img: assets/img/stereo_ov.png
importance: 2
category: Graduate
---

## 📌 Project: Stereo Camera Calibration Accuracy Comparison

> ✔ RMSE 0.6 px 달성  
> ✔ 소량 데이터에서도 안정적 캘리브레이션
---

### 1. 연구 필요성 (Background)
- 기존 카메라 캘리브레이션은 Intrinsic–Extrinsic 분리 추정 방식으로 인해 오차 누적 문제 발생
- 특히 파라미터 추정 과정에서 발생하는 비선형 오차와 데이터 부족 환경에서의 성능 저하 한계 존재
- 이를 해결하기 위해 3차원 특징점 기반 통합 최적화 캘리브레이션 기법 필요

---

### 2. 연구 내용 (Approach)
- FLIR Bumblebee XB3 기반 스테레오 카메라 영상 획득 시스템 구축
- FlyCap2 API를 활용한 C++ 기반 영상 수집 및 처리 파이프라인 구현
- 체스보드 패턴(9×6)을 활용한 특징점 추출 및 캘리브레이션 입력 데이터 구성
- 카메라 내부/외부 파라미터와 3D 특징점을 동시에 추정하는 통합 최적화 모델 설계
- 비선형 관측 모델을 테일러 전개 기반으로 선형화 후 최소자승 반복 최적화 적용

---

### 3. 실험 결과 (Experiment)
- 다양한 거리 및 촬영 조건에서 캘리브레이션 수행
- 데이터 수 변화(특징점 약 100개 수준) 환경에서 성능 비교 분석
- 제한된 데이터 환경에서도 안정적인 캘리브레이션 수행 가능성 검증

---

### 4. 성과 (Results / Contribution)
- 평균 약 0.6 px 수준의 캘리브레이션 RMSE 확보
- 초점거리 약 2% 이하, Baseline 약 0.53% 이하 오차 수준 파라미터 추정
- 소량 데이터(이미지 2쌍)에서도 평균 약 2.7 px RMSE 확보
- 스테레오 카메라 캘리브레이션 알고리즘 설계 및 구현
- 국내 학술대회(제어로봇시스템학회, 2025) 발표

---

### 5. 사용 Tool (Tech Stack)
- Language: C++
- Library: OpenCV
- API: FlyCap2
- Sensor: FLIR Bumblebee XB3

<div class="row">
<div class="row">
    <div class="col-sm mt-3 mt-md-0 text-center">
        {% include figure.liquid path="assets/img/stereo_ov.png" class="img-fluid rounded z-depth-1" %}
        <div class="caption">[ 전체 시스템 구조 ]</div>
    </div>

    <div class="col-sm mt-3 mt-md-0 text-center">
        {% include figure.liquid path="assets/img/sensor.jpg" class="img-fluid rounded z-depth-1" %}
        <div class="caption">[ 센서 구성 ]</div>
    </div>

    <div class="col-sm mt-3 mt-md-0 text-center">
        {% include figure.liquid path="assets/img/stereo_result.png" class="img-fluid rounded z-depth-1" %}
        <div class="caption">[ 실험 결과 ]</div>
    </div>

    <div class="col-sm mt-3 mt-md-0 text-center">
        {% include figure.liquid path="assets/img/stereo_ov_detail.png" class="img-fluid rounded z-depth-1" %}
        <div class="caption">[ 최적화 구조 ]</div>
    </div>
</div>
