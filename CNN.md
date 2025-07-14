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









