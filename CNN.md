# 🧠 definition of terms CNN

| 용어 | 설명 |
|------|------|
| **CNN (Convolutional Neural Network)** | 이미지 분석에 특화된 인공신경망 |
| **Convolution (합성곱)** | 필터를 통해 특징을 추출하는 연산 |
| **Kernel / Filter** | 입력 이미지에 적용되는 작은 행렬로, 특징을 감지 |
| **Stride** | 필터를 이동시키는 간격. 값이 크면 출력 크기가 작아짐 |
| **Padding** | 입력 가장자리에 값을 추가해 출력 크기를 조절 |
| **Feature Map** | Convolution 결과로 나온 출력 이미지 |
| **ReLU (Rectified Linear Unit)** | 음수를 0으로, 양수는 그대로 유지하는 비선형 함수 |
| **Pooling** | 공간 크기를 줄이며 주요 정보만 남기는 과정 (Max, Average) |
| **Flatten** | 2D 데이터를 1D로 펼치는 과정 |
| **Fully Connected Layer** | 모든 뉴런이 연결된 일반적인 신경망 계층 |
| **Epoch** | 전체 데이터셋을 한 번 학습시키는 횟수 |
| **Batch Size** | 한 번에 학습하는 데이터 샘플 수 |
| **Loss Function** | 예측값과 정답값의 차이를 계산하는 함수 |
| **Backpropagation** | 손실을 기반으로 가중치를 업데이트하는 과정 |
| **Optimizer** | 손실을 최소화하기 위해 파라미터를 조정하는 알고리즘 |

![CNN 구조](https://upload.wikimedia.org/wikipedia/commons/6/63/Typical_cnn.png)


# CNN(Convolutional Neural Network) 설명
## CNN(Convolutional Neural Network, 합성곱 신경망)은 이미지나 영상, 시계열 데이터와 같은 2차원 또는 3차원 데이터 처리에 특화된 딥러닝 모델입니다. 컴퓨터 비전 분야에서 매우 널리 사용되며, 특히 이미지 분류, 객체 탐지, 얼굴 인식, 자율주행 등에서 강력한 성능을 보입니다.

### 1단계: 이미지 업로드 및 색상값 추출
<img width="1626" height="689" alt="image" src="https://github.com/user-attachments/assets/fe65b07a-8a24-498a-abd2-d1a012a4a31b" />

### 2단계: 수직 엣지 감지 필터
<img width="1626" height="688" alt="image" src="https://github.com/user-attachments/assets/dd41a753-9e56-4ae4-938a-db77a67f10dc" />

### 3단계: 수평 엣지 감지 필터
<img width="1622" height="687" alt="image" src="https://github.com/user-attachments/assets/6ed75a14-4366-4778-82b3-f57905d2c3ba" />

### 4단계: 블러 필터
<img width="1622" height="686" alt="image" src="https://github.com/user-attachments/assets/e83662d4-3050-46c0-8196-db4eaed5bd98" />

### 5단계: 샤프닝 필터
<img width="1623" height="691" alt="image" src="https://github.com/user-attachments/assets/36bfb6f4-9f39-4bd8-8aeb-9308c17ce381" />

### 최종 결과:
<img width="1619" height="505" alt="image" src="https://github.com/user-attachments/assets/2230e226-bb70-42a4-a56a-704e9e5c3e9a" />

## 1️⃣ 입력 (Input)

- **예시**: `28x28` 흑백 이미지 or `224x224x3` 컬러 이미지
- **목적**: 모델이 처리할 수 있는 형식으로 이미지 입력

---

## 2️⃣ 전처리 (Preprocessing)

- **정규화 (Normalization)**: 픽셀 값을 0~1로 조정 (`x / 255.0`)
- **크기 조정 (Resize)**: 모델에 맞는 이미지 크기로 조정 (예: `224x224`)
- **데이터 증강 (Augmentation)**: 학습 데이터 다양성을 위한 회전, 뒤집기 등 (훈련 시에만)

---

## 3️⃣ 합성곱 계층 (Convolution Layer)

- **역할**: 필터(kernel)를 사용하여 이미지에서 특징 추출
- **출력**: Feature Map (특징 맵)
- **하이퍼파라미터**: 필터 수, 커널 크기, stride, padding

---

## 4️⃣ 활성화 함수 (ReLU)

- **역할**: 비선형성 도입
- **ReLU**: `f(x) = max(0, x)`
- **이유**: 신경망이 더 복잡한 표현을 학습 가능하게 함

---

## 5️⃣ 풀링 계층 (Pooling Layer)

- **Max Pooling**: 일정 영역 내 최대값만 추출
- **Average Pooling**: 평균값 추출
- **목적**:
  - 공간적 크기 감소 (연산량 줄이기)
  - 과적합 방지
  - 특징 추출 강화

---

## 6️⃣ 계층 반복 (Convolution + Pooling 반복)

- 여러 층을 반복적으로 쌓아
  - **저수준 특징** (모서리, 선 등) → **고수준 특징** (눈, 얼굴 등) 추출
- **깊이가 깊어질수록 더 복잡한 특징 학습**

---

## 7️⃣ 플래튼 (Flatten Layer)

- 2D Feature Map을 1D 벡터로 변환
- **Fully Connected Layer**로 입력되기 위해 필요

---

## 8️⃣ 완전 연결 계층 (Fully Connected Layer)

- 일반적인 인공신경망 구조
- 모든 노드가 연결됨
- 최종 분류/회귀 결과를 출력

---

## 9️⃣ 출력 (Output Layer)

- **Softmax 함수**: 다중 클래스 분류 시 사용
- **Sigmoid 함수**: 이진 분류
- 출력은 클래스별 확률 값으로 표현됨

---

## 🖼️ 시각화 예시

![cnn-pipeline](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*XizfU1KjvM3YZodL4jFqaw.png)

## 🏁 요약

| 단계 | 설명 |
|------|------|
| 입력 | 이미지 데이터 입력 |
| 전처리 | 정규화, 리사이징, 증강 |
| Convolution | 특징 추출 |
| ReLU | 비선형성 추가 |
| Pooling | 공간 축소, 특징 강화 |
| Flatten | FC 계층을 위한 1D 변환 |
| FC Layer | 분류 결정 |
| 출력 | Softmax로 클래스 예측 |








