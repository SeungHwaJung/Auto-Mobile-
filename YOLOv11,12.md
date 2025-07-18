## 📊 비교 표

| 항목                      | YOLOv11 (YOLO-NAS 기반)                        | YOLOv12 (YOLO-World 기반)                      |
|---------------------------|-----------------------------------------------|-----------------------------------------------|
| 🧠 주요 특징              | NAS 기반 최적화<br>실시간 성능 개선             | 멀티모달 처리<br>Open Vocabulary 탐지 지원     |
| 📦 백본 (Backbone)        | NASNet, EfficientNet 변형                      | CLIP Vision Transformer 등                    |
| 🧰 입력 형식              | 이미지 단독 입력                               | 이미지 + 텍스트 (멀티모달)                    |
| 📚 학습 방식              | 지도학습 (Supervised Learning)                 | Zero-shot / Few-shot                         |
| ⚙️ 탐지 특징              | 고정 클래스 탐지                              | 클래스 이름 없이 탐지 가능 (텍스트 설명 기반) |
| 🛠️ 적용 분야              | CCTV, 자율주행, 드론                           | 검색 시스템, 유튜브 분석, AI 비서              |
| ⚡ 라이브러리 / 프레임워크 | `ultralytics`, `super-gradients`              | `GroundingDINO`, `CLIP`, `SAM`                |
| 📎 대표 프로젝트          | [YOLO-NAS](https://github.com/Deci-AI/super-gradients) | [YOLO-World](https://github.com/tencent-ailab/yolo-world) |

---

## 🧩 개념 요약

| 용어             | 설명 |
|------------------|------|
| **YOLO**         | You Only Look Once – 빠른 객체 탐지 모델 |
| **NAS**          | Neural Architecture Search – 최적 모델 구조 자동 탐색 |
| **멀티모달**      | 이미지 + 텍스트처럼 다양한 입력 통합 분석 |
| **Zero-shot**    | 새로운 객체를 학습 없이 탐지하는 방식 |
| **Open Vocabulary** | 클래스가 사전 정의되지 않아도 탐지 가능 |
