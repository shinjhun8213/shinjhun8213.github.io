---
title: 'NeRF: Neural Radiance Fields 논문 리뷰'
date: 2025-10-25
permalink: /posts/2025/10/nerf-review/
tags:
  - nerf
  - 3d-vision
  - view-synthesis
  - deep-learning
categories:
  - paper-review
  - foundational
---

NeRF(Neural Radiance Fields)는 2020년 ECCV에서 발표된 3D vision 분야의 획기적인 논문입니다. 5D 좌표로부터 색상과 밀도를 출력하는 MLP를 사용하여 새로운 시점을 합성합니다.

## 논문 정보

**제목**: NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis  
**저자**: Ben Mildenhall et al. (UC Berkeley, Google Research)  
**학회**: ECCV 2020 (Best Paper Honorable Mention)  
**논문**: [arXiv](https://arxiv.org/abs/2003.08934)  
**코드**: [GitHub](https://github.com/bmild/nerf)  
**프로젝트**: [홈페이지](https://www.matthewtancik.com/nerf)

## 핵심 기여

1. **5D Neural Radiance Field**: 위치(x,y,z) + 방향(θ,φ)을 입력받아 색상과 밀도 출력
2. **Positional Encoding**: 고주파 디테일 학습을 위한 위치 인코딩 (PSNR 5dB 향상)
3. **Hierarchical Volume Sampling**: Coarse-to-fine 샘플링으로 렌더링 효율 개선
4. **SOTA 성능**: 모든 벤치마크에서 압도적 성능

## 방법론

### Neural Radiance Field 표현

연속적인 volumetric scene을 MLP \(F_\Theta\)로 표현:

\[ F_\Theta: (\mathbf{x}, \mathbf{d}) \to (\mathbf{c}, \sigma) \]

- 입력: 3D 위치 \(\mathbf{x}\), 2D 방향 \(\mathbf{d}\)
- 출력: RGB 색상 \(\mathbf{c}\), 볼륨 밀도 \(\sigma\)

### Volume Rendering

카메라 광선을 따라 색상 적분:

\[ C(\mathbf{r}) = \int_{t_n}^{t_f} T(t) \cdot \sigma(\mathbf{r}(t)) \cdot \mathbf{c}(\mathbf{r}(t), \mathbf{d}) \, dt \]

실제로는 64개 샘플로 수치 적분 수행.

### Positional Encoding (핵심!)

고주파 디테일을 위해 입력을 고차원 공간으로 매핑:

\[ \gamma(p) = (\sin(2^0\pi p), \cos(2^0\pi p), \ldots, \sin(2^{L-1}\pi p), \cos(2^{L-1}\pi p)) \]

- 위치: L=10 (60차원)
- 방향: L=4 (24차원)

**이게 없으면 흐릿한 결과만 나옴!**

## 실험 결과

| 데이터셋 | PSNR ↑ | SSIM ↑ | LPIPS ↓ |
|---------|--------|--------|---------|
| SRN | 22.26 | 0.846 | 0.170 |
| LLFF | 24.88 | 0.911 | 0.114 |
| **NeRF** | **31.01** | **0.947** | **0.081** |

→ 6dB PSNR 향상은 시각적으로 엄청난 차이!

## 산업공학 관점

### 제조업 응용 가능성

1. **디지털 트윈**: 공장 설비 사진으로 3D 환경 자동 재구성
2. **품질 검사**: 다양한 각도의 합성 이미지로 학습 데이터 증강
3. **AR 매뉴얼**: 설비 스캔으로 작업자 시점 가이드 생성
4. **VR 안전 교육**: 위험 상황 시뮬레이션 환경 구축

### 한계와 개선 방향

- 렌더링 느림 (이미지당 30초) → 3D Gaussian Splatting으로 해결
- 정적 장면만 가능 → Dynamic NeRF 연구 필요
- 센서 데이터 융합 연구 가치 있음

## 후속 연구

- **Instant-NGP** (2022): 1000배 가속
- **3D Gaussian Splatting** (2023): 실시간 렌더링
- **DreamFusion** (2023): Text-to-3D 생성

## 개인 평가

**혁신성**: ⭐⭐⭐⭐⭐  
**실용성**: ⭐⭐⭐  
**재현성**: ⭐⭐⭐⭐

3D vision 연구의 출발점이자 필독 논문. Positional encoding의 중요성을 깨달았고, implicit representation의 강력함을 확인.

## 다음에 읽을 논문

- [ ] 3D Gaussian Splatting (실시간 개선)
- [ ] Instant-NGP (속도 개선)
- [ ] UNIST 센서 융합 논문과 비교

---

**참고자료**  
- [xoft 블로그 NeRF 설명](https://xoft.tistory.com/2)  
- [공식 구현](https://github.com/bmild/nerf)
