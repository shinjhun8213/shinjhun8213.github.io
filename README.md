# 3D Vision & Industrial AI - 논문 리뷰

3D vision, 생성 모델, 제조업 AI 관련 논문을 정리한 저장소입니다.

## 🎯 연구 관심사

- **3D Vision**: NeRF, 3D Gaussian Splatting, Neural Rendering
- **생성 모델**: Diffusion Models, Text-to-3D Generation
- **산업 응용**: 디지털 트윈, 품질 검사, AR/VR 제조 교육
- **XR 기술**: 실시간 렌더링, 공간 컴퓨팅

## 📚 논문 리뷰 (카테고리별)

### 🏗 Foundational Papers
핵심 기초 이론 논문

| 논문 | 학회/연도 | 주요 기여 | 리뷰 | 코드 |
|------|----------|----------|------|------|
| NeRF: Neural Radiance Fields | ECCV 2020 | 5D implicit representation | [리뷰](papers/foundational/nerf-2020.md) | [GitHub](https://github.com/bmild/nerf) |
| 3D Gaussian Splatting | SIGGRAPH 2023 | 실시간 렌더링 | [리뷰](papers/foundational/3dgs-2023.md) | [GitHub](https://github.com/graphdeco-inria/gaussian-splatting) |
| Instant-NGP | SIGGRAPH 2022 | 멀티해상도 해시 인코딩 | [리뷰](papers/foundational/instant-ngp-2022.md) | [GitHub](https://github.com/NVlabs/instant-ngp) |

### 🎨 Text-to-3D Generation
텍스트로부터 3D 생성

| 논문 | 학회/연도 | 주요 기여 | 리뷰 | 우선순위 |
|------|----------|----------|------|---------|
| DreamFusion | ICLR 2023 | SDS (Score Distillation Sampling) | [리뷰](papers/text-to-3d/dreamfusion-2023.md) | ⭐⭐⭐⭐⭐ |
| Instant3D | NeurIPS 2024 | 25ms 실시간 생성 | [리뷰](papers/text-to-3d/instant3d-2024.md) | ⭐⭐⭐⭐ |
| LangSplat | CVPR 2024 | 언어 기반 3DGS | [리뷰](papers/text-to-3d/langsplat-2024.md) | ⭐⭐⭐⭐ |

### 🏭 Industrial Applications
제조업/산업 응용

| 논문 | 학회/연도 | 응용 분야 | 리뷰 | 실용성 |
|------|----------|----------|------|--------|
| Multimodal Sensor-Guided Diffusion | - 2024 | 가공 표면 합성 | [리뷰](papers/industrial/unist-sensor-diffusion.md) | ⭐⭐⭐⭐⭐ |
| LiDAR-GS | - 2024 | 자율주행 시뮬레이션 | [리뷰](papers/industrial/lidar-gs-2024.md) | ⭐⭐⭐⭐ |

### 🔎 Survey Papers
분야 전체를 조망하는 서베이

| 논문 | 발표/연도 | 범위 | 리뷰 | 추천도 |
|------|----------|------|------|--------|
| Diffusion Models in 3D Vision | arXiv 2024 | 3D vision에서의 diffusion | [리뷰](papers/survey/diffusion-3dvision-2024.md) | ⭐⭐⭐⭐⭐ |
| Text-to-3D Shape Generation | STAR 2024 | T2-3D 전반 | [리뷰](papers/survey/text-to-3d-survey.md) | ⭐⭐⭐⭐ |

## 🏷 태그별 분류

- [#nerf](tags/nerf.md) (12편)
- [#3dgs](tags/3dgs.md) (8편)
- [#diffusion](tags/diffusion.md) (15편)
- [#text-to-3d](tags/text-to-3d.md) (10편)
- [#manufacturing](tags/manufacturing.md) (5편)
- [#realtime-rendering](tags/realtime.md) (7편)
