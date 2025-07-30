# PeopleNet Overview

PeopleNet은 NVIDIA가 개발한 실시간 사람 감지 모델로, 다음과 같은 특징이 있습니다:

- TLT로 사전 학습된 ResNet34 백본 기반
- TensorRT 최적화로 실시간 처리 가능
- 일반적인 "사람" 감지에 특화

활용 예:
- CCTV 사람 수 카운팅
- 접근 금지 구역 침입 감지
- 스마트시티 인프라

# NVIDIA PeopleNet 모델 정리 및 데모

NVIDIA PeopleNet은 실시간 사람 감지를 위한 고성능 딥러닝 모델입니다. 이 리포지토리는 PeopleNet의 개요, 사용 방법, 예제 코드를 포함하여 정리되어 있습니다.

---

## 📌 모델 개요

| 항목 | 설명 |
|------|------|
| 이름 | PeopleNet |
| 개발사 | NVIDIA |
| 목적 | 사람 탐지 (human detection) |
| 클래스 | person |
| 출력 | Bounding boxes, confidence scores |
| 사용 도구 | ONNX, TensorRT, DeepStream SDK 등 |
| 라이센스 | NVIDIA NGC 사용 약관 참고 |

---

## 📦 모델 다운로드 (NVIDIA NGC)

- 공식 NGC 링크:  
  🔗 https://catalog.ngc.nvidia.com/orgs/nvidia/teams/tlt/models/peoplenet

### CLI로 다운로드 (권장)

```bash
ngc registry model download-version nvidia/tlt_peoplenet:deployable_v2.1

또는 직접 ONNX 모델 사용 시:
wget https://<model_download_link>

## 코드 실행을 위해서는 일단
pip install -r requirements.txt 을 실행 후
python inference/peoplenet_infer.py --model models/resnet34_peoplenet_int8.onnx --video input.mp4
비디오 업로드

| 폴더           | 설명                           |
| ------------ | ---------------------------- |
| `models/`    | ONNX 또는 TensorRT 엔진 파일 저장 위치 |
| `inference/` | 추론 스크립트 저장                   |
| `notebooks/` | Jupyter 데모 노트북               |
| `images/`    | 결과 이미지 저장                    |
| `docs/`      | PeopleNet 관련 이론 정리           |

# 예시
import onnxruntime as ort
import cv2
import numpy as np
import argparse
import os

def preprocess(image, input_shape=(3, 544, 960)):
    resized = cv2.resize(image, (input_shape[2], input_shape[1]))
    img = resized / 255.0
    img = img.transpose(2, 0, 1)[np.newaxis, :].astype(np.float32)
    return img

def postprocess(outputs, conf_threshold=0.5):
    # 예시용. 실제 PeopleNet의 출력 구조에 맞게 후처리 필요.
    return []

def draw_results(image, detections):
    for det in detections:
        x1, y1, x2, y2, conf = det
        cv2.rectangle(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
        cv2.putText(image, f"{conf:.2f}", (x1, y1 - 5),
                    cv2.FONT_HERSHEY_SIMPLEX, 0.5, (0, 255, 0), 1)
    return image

def run(model_path, video_path):
    session = ort.InferenceSession(model_path)
    input_name = session.get_inputs()[0].name

    cap = cv2.VideoCapture(video_path)
    os.makedirs("output", exist_ok=True)
    out = cv2.VideoWriter("output/result.avi",
                          cv2.VideoWriter_fourcc(*'XVID'),
                          30, (int(cap.get(3)), int(cap.get(4))))

    while cap.isOpened():
        ret, frame = cap.read()
        if not ret:
            break
        input_tensor = preprocess(frame)
        outputs = session.run(None, {input_name: input_tensor})
        detections = postprocess(outputs)
        result = draw_results(frame, detections)
        out.write(result)

    cap.release()
    out.release()

if __name__ == "__main__":
    parser = argparse.ArgumentParser()
    parser.add_argument('--model', required=True, help='Path to ONNX model')
    parser.add_argument('--video', required=True, help='Path to input video')
    args = parser.parse_args()
    run(args.model, args.video)
