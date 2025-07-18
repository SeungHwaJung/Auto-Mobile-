> **YOLO (You Only Look Once)**는 단일 신경망으로 이미지에서 객체를 실시간으로 탐지하는 딥러닝 알고리즘입니다.  
> 본 저장소는 최신 YOLOv8 기반으로 객체 탐지 프로젝트를 구성하며, 이미지/영상/웹캠 등 다양한 소스에 적용하는 방법을 안내합니다.

## 🔍 What is YOLO?

**YOLO**는 입력 이미지 전체를 단 한 번(One-shot)에 처리하여 **객체 위치(Box)**와 **클래스(Class)**를 예측하는 객체 탐지(Object Detection) 알고리즘입니다.

- 기존 R-CNN 계열보다 수백 배 빠름
- 실시간 애플리케이션에 적합
- 최신 버전은 **YOLOv8 (Ultralytics)**

---

## 🚀 YOLOv8의 주요 특징

| 항목 | 설명 |
|------|------|
| ⚡ 속도 | 실시간 추론 가능 (30~100 FPS) |
| 🧠 단일 네트워크 구조 | 백본 + 넥 + 헤드 일체형 |
| 🔍 높은 정확도 | COCO 기준 높은 mAP 성능 |
| 🛠 다양한 태스크 지원 | Detection, Segmentation, Pose, Classification |
| 📦 배포 용이 | ONNX, TensorRT, CoreML 등으로 내보내기 가능 |
| 🔧 커스텀 훈련 쉬움 | 커스텀 데이터로 손쉽게 학습 가능 |
| 📱 엣지 디바이스 최적화 | Jetson, Android, Raspberry Pi 대응 |

---

## 📦 설치 방법 (Colab or Local)

```bash
# 최신 YOLOv8 라이브러리 설치
pip install ultralytics
```
## 📦 설치 방법 (Colab or Local)

| 프로젝트              | 설명                                        |
|-----------------------|---------------------------------------------|
| 📦 스마트 창고 감시    | 위험 요소, 사람, 박스 등 실시간 탐지        |
| 🛑 교통 표지판 탐지    | 차량, 신호등, 보행자 등 교통 객체 인식      |
| 🤖 로봇 비전           | 로봇 내비게이션 및 환경 인식에 활용         |
| 🏭 산업 안전 감시      | 헬멧 미착용, 위험 구역 접근 등 탐지         |
| 📱 모바일 OCR 연동     | 객체 + 문자 인식 결합형 앱 개발            |
| 🎥 유튜브 영상 분석    | 영상 속 객체 통계 및 이상 탐지 자동화       |

## 모델별 성능 비교 (YOLOv8 계열)****

| 모델       | 크기      | 속도(FPS) | 정확도(mAP)     |
|------------|-----------|------------|-----------------|
| yolov8n    | 매우 작음 | ✅✅✅✅✅  | ❌❌              |
| yolov8s    | 작음      | ✅✅✅✅   | ✅✅              |
| yolov8m    | 중간      | ✅✅✅     | ✅✅✅            |
| yolov8l    | 큼        | ✅✅       | ✅✅✅✅          |
| yolov8x    | 매우 큼   | ✅         | ✅✅✅✅✅        |

## 내보내기 포맷

| 포맷       | 설명                           |
|------------|--------------------------------|
| ONNX       | 범용 AI 추론 엔진에서 사용     |
| TensorRT   | NVIDIA GPU용 고속 추론 포맷    |
| CoreML     | Apple 기기에서 동작            |
| TFLite     | Android 등 모바일 환경 사용    |

## YOLOv8 + 임베디드 시스템 연계

| 항목            | 설명                                                                 |
|-----------------|----------------------------------------------------------------------|
| 💡 프로젝트 명    | Jetson Nano 기반 실시간 객체 탐지 시스템                              |
| 🎯 목적          | 임베디드 환경에서 카메라 입력을 처리하여 YOLOv8로 객체 탐지 수행       |
| 🧠 AI 모델       | Ultralytics YOLOv8n (경량화 모델, 엣지 디바이스용)                    |
| ⚙️ 임베디드 보드  | NVIDIA Jetson Nano / Raspberry Pi 4 + Coral TPU                       |
| 📸 입력 장치      | CSI 카메라, USB 웹캠                                                  |
| 🔌 출력 장치      | LCD 디스플레이, 부저, LED, 모터 등 (GPIO 연동)                        |
| 🧩 주요 기술       | PyTorch, OpenCV, GPIO 제어, UART, PWM, 실시간 멀티스레딩             |
| 📶 연동 예시      | 탐지 결과에 따라 부저 울림, LED 점등, 경고 메시지 출력                |
| 🛠 실용 응용       | 스마트 감시카메라, 안전모 미착용 감지, 장애물 회피 자율 로봇          |

## 시스템 아키텍처 요약

| 구성 요소         | 설명                                                      |
|------------------|-----------------------------------------------------------|
| 📷 카메라 입력     | 실시간 프레임 캡처 (CSI/USB)                              |
| 🧠 YOLOv8 추론     | 프레임별 객체 탐지 및 좌표/클래스 반환                     |
| ⚙️ Jetson 처리     | YOLO 결과 분석 → GPIO 제어 로직 실행                       |
| 💡 출력 장치       | 탐지 이벤트 발생 시 LED 점등 / 부저 / LCD 경고            |
| 🔗 외부 통신       | UART 또는 Wi-Fi로 외부 마이컴/서버에 결과 전송 가능         |

## 전자공학과 학습 내용과 연관성

| 전자공학 전공 과목     | 프로젝트 내 적용 예                                         |
|------------------------|-------------------------------------------------------------|
| 마이크로프로세서        | Jetson Nano, Raspberry Pi, GPIO 제어                          |
| 임베디드 시스템         | 리눅스 기반 장치 드라이버, 실시간 제어, 인터럽트              |
| 신호 및 시스템          | 영상 신호의 실시간 처리, 입력 시퀀스 분석                    |
| 센서 및 액추에이터      | 카메라, 초음파, 부저, 모터 등 주변 장치 연동                  |
| 디지털 시스템 설계      | 탐지 결과 기반 제어 로직 설계 (논리회로처럼 분기)              |
| 컴퓨터 비전 / 머신러닝 | YOLOv8 객체 인식 알고리즘 이해 및 적용                       |


