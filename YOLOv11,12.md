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
