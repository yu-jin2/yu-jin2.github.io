---
layout: page
title:  LSTM 기반 다중 서빙 로봇 목적지 병합 배차 시스템
description:
img: assets/img/lstm_1.jpg
importance: 5
category: Undergraduate
---

## 📌 Project: LSTM 기반 다중 서빙 로봇 목적지 병합 배차 시스템

> ✔ LSTM 기반 조리시간 예측 오차 약 33% 개선 (MAE 기준)  
> ✔ 다중 로봇 배차 최적화 시 평균 대기시간 약 39% 감소
---

### 1. 연구 필요성 (Background)
- 기존 서빙 로봇 배차 시스템은 현재 시점의 정적 정보만을 기반으로 의사결정을 수행하여 시간 흐름에 따른 주방 혼잡도와 주문 패턴을 반영하지 못함
-기존 서빙 로봇 배차 시스템은 현재 시점의 정적 정보만을 기반으로 의사결정을 수행하여 시간 흐름에 따른 주방 혼잡도와 주문 패턴을 반영하지 못함
- 특히 조리시간은 단순한 현재 상태보다 직전 주문 흐름과 주방 부하의 누적 효과에 크게 영향을 받는 시계열적 특성을 가짐
- 이에 따라 시계열 패턴을 학습할 수 있는 LSTM 기반 예측과 배차 최적화를 결합한 시스템 필요

---

### 2. 연구 내용 (Approach)
- 대형 식당 환경을 가정한 시뮬레이션 기반 다중 서빙 로봇 시스템 설계 (3대 로봇, 다구역 구조)
- 주문 흐름 기반 hidden state(주방 혼잡도, 구역별 수요, 메뉴 반복 패턴 등)를 반영한 시계열 데이터 생성 모델 구축
- LSTM을 활용하여 조리시간 및 식사시간 예측 모델 구현
- 비교군으로 현재 시점 정보만을 사용하는 Linear Regression 기반 모델 구성
- 예측된 완료 시점을 기반으로 주문 간 병합(batch serving) 가능한 로봇 배차 알고리즘 설계
- 시간 근접성 및 공간 거리 기반 목적지 병합 전략 적용

---

### 3. 실험 결과 (Experiment)
- 시뮬레이션 환경에서 LSTM과 비시계열 모델 간 예측 성능 및 배차 성능 비교 수행
- 조리시간(Cook Time)과 식사시간(Meal Time)에 대해 각각 예측 정확도 평가
- 예측 결과를 기반으로 실제 서빙 시작 시간과 대기시간을 계산하여 배차 효율 분석

---

### 4. 성과 (Results / Contribution)
- 조리시간(Cook Time)은 강한 시계열 의존성을 가지며 LSTM이 효과적임을 확인
→ MAE 기준 약 33% 오차 감소
- 식사시간(Meal Time)은 시계열 의존성이 상대적으로 낮아 LSTM의 효과가 제한적임을 확인
- LSTM 기반 예측을 적용한 배차 시스템에서 평균 대기시간 약 39% 감소
- 시계열 예측이 실제 로봇 운영 효율 개선으로 직접 연결됨을 실험적으로 검증

---

### 5. 사용 Tool (Tech Stack)
- Language: Python
- Library: TensorFlow (LSTM), Scikit-learn, Pandas, NumPy, Matplotlib
- Environment: Google Colab
- Algorithm: LSTM 기반 시계열 예측, Linear Regression 비교 모델
- System: Multi-Robot Dispatch Simulation (Batch Scheduling, Greedy Optimization)

<div class="row">
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid loading="eager" path="assets/img/lstm_2.jpg" class="img-fluid rounded z-depth-1" %}
    <div class="caption">[ 다중 로봇 서빙 스케줄 최적화 비교 ]</div>
  </div>
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid loading="eager" path="assets/img/lstm_1.jpg" class="img-fluid rounded z-depth-1" %}
    <div class="caption">[ 배차 최적화에 따른 대기시간 분포 개선 ]</div>
  </div>
  <div class="col-sm mt-3 mt-md-0 text-center">
    {% include figure.liquid loading="eager" path="assets/img/lstm_3.jpg" class="img-fluid rounded z-depth-1" %}
    <div class="caption">[ 조리시간 예측 정확도 향상 비교 ]</div>
  </div>
</div>
