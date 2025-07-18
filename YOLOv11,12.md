| 버전 | 요약 설명 |
|------|------------|
| **YOLOv11** | 기존 YOLO를 NAS(Neural Architecture Search) 기술로 최적화한 고속·고정밀 객체 탐지 모델. 주로 `YOLO-NAS`로 불림. |
| **YOLOv12** | 텍스트로 객체를 탐지하는 멀티모달 모델. 기존 YOLO의 구조를 넘어서 Open Vocabulary 탐지를 수행. `YOLO-World`, `GroundingDINO`, `CLIP` 등이 기반. |

---

## 🧠 YOLOv11 (YOLO-NAS 기반)

- **공식 YOLO는 아니며, YOLO-NAS로 대표됨**
- NAS 기반으로 YOLO 구조를 자동 최적화
- `super-gradients` 라이브러리를 통해 사용 가능

### 🔧 핵심 기술
- Neural Architecture Search (NAS)
- 경량화된 구조: YOLO-NAS-S / M / L
- 기존 YOLOv8 대비 **정확도 + 속도 향상**

### 💡 주요 특징
- 실시간 객체 탐지에 적합
- 높은 FPS와 정확도를 동시에 달성
- COCO 벤치마크에서 SOTA급 성능

---

## 🧠 YOLOv12 (YOLO-World / GroundingDINO 기반)

- **YOLOv12는 멀티모달 객체 탐지 모델**
- 기존 YOLO와 달리 **텍스트 기반 객체 탐지** 가능
- 사전에 학습하지 않은 클래스도 탐지 (Open Vocabulary)

### 🔧 핵심 기술
- CLIP (이미지-텍스트 임베딩)
- GroundingDINO (텍스트 기반 객체 탐지)
- Segment Anything (픽셀 단위 분할)
- YOLO-World (Tencent)

### 💡 주요 특징
- "red car", "police officer" 등 텍스트로 탐지 가능
- Zero-shot / Few-shot 탐지 가능
- 검색, 보안 분석, 영상 요약 등 고차원 응용 가능

---

## 📊 YOLOv11 vs YOLOv12 비교표

| 항목               | YOLOv11 (YOLO-NAS)                     | YOLOv12 (YOLO-World 등)                     |
|--------------------|----------------------------------------|---------------------------------------------|
| 구조 기반           | YOLOv8 확장 + NAS 최적화               | CLIP + Transformer + SAM 등 복합 구조       |
| 주요 특징           | 빠름 + 정확함 + 경량화                 | 텍스트 기반 탐지 + Open Vocabulary 지원     |
| 입력 방식           | 이미지 단독                           | 이미지 + 텍스트 (멀티모달)                  |
| 클래스 인식 방식     | 고정 클래스 탐지 (학습된 것만)         | 프롬프트 기반 객체 탐지 (학습 안 해도 탐지) |
| 활용 예시           | CCTV, 자율주행, 드론 등               | 영상 검색, 설명, AI 비서, 유튜브 분석 등    |
| 실행 라이브러리     | `super-gradients`                     | `GroundingDINO`, `CLIP`, `SAM` 등           |

## 📌 벤치마크 개요

| 항목 | YOLOv8 | YOLOv11 (YOLO-NAS) | YOLOv12 (YOLO-World) |
|------|--------|---------------------|------------------------|
| 🎯 **mAP@0.5** | 50.2% | **52.3%** ✅ | 51.8% |
| ⚡ **FPS** | 95 | **103** ✅ | 47 |
| 🧠 **파라미터 수 (백만)** | 12.3M | **11.7M** ✅ | 75.2M |

> 🧪 참고: 모든 모델은 COCO 데이터셋 기준으로 테스트되었으며, 정확도(mAP), 속도(FPS), 모델 크기(Params)를 비교합니다.

---

## 📈 성능 그래프

![YOLO Benchmark](<img width="895" height="336" alt="bench" src="https://github.com/user-attachments/assets/902562a1-0089-4c6a-9994-8898d013cb5a" />
)

---

## 📌 주요 해석 요약

- ✅ **YOLOv11 (YOLO-NAS)**: 정확도와 속도, 모델 경량화를 모두 달성한 최적 객체 탐지 모델
- 🧠 **YOLOv12 (YOLO-World)**: 정확도는 유사하지만 **Open Vocabulary 탐지**가 가능한 유연한 멀티모달 모델
- ⚖️ **YOLOv8**: 기본 YOLO의 균형 잡힌 성능 제공

## 🔚 결론

| 모델 | 한 줄 요약 |
|------|-------------|
| YOLOv11 | YOLOv8을 NAS로 강화한 고성능 실시간 탐지기 |
| YOLOv12 | YOLO를 넘은 텍스트 기반 멀티모달 탐지기 |
