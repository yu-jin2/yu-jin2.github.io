---
layout: page
title: 스테레오 카메라와 2D LiDAR 통합 캘리브레이션
description:
img: assets/img/12.jpg
importance: 1
category: Graduate
---

[센서 퓨전 및 정합성 검증]
• 주요 역할: 이종 센서 간 데이터 정합성 향상을 위한 최적화 알고리즘 개발 및 검증
• 사용 기술: C++, Optimization Algorithms, Stereo Camera, 2D LiDAR
• 수행 내용 및 성과:
- 카메라 정밀 보정: 내외부 파라미터와 3차원 좌표를 통합 추정하는 최적화 구조 제안으로 재투영 오차(Reprojection Error) 1픽셀 미만 달성.
- 이종 센서 통합 정합: 라이다의 반사 강도(Reflectivity) 데이터를 활용한 체스보드 패턴 인식 기법을 적용하여 카메라-라이다 간 매칭 쌍 확대 및 정밀 보정 수행.
- 수치 기반 검증: 개발 알고리즘을 통해 실측값 대비 평균 1cm 이내의 정합 정확도 확보 및 신뢰성 정량화.
- 직무 연계 역량: 센서 인식의 물리적 한계를 고려한 허용 오차 정의 역량 확보 및 ADAS(LKA, FCA 등) 기능 오작동 방지를 위한 Fallback 설계 논리 구축.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>
