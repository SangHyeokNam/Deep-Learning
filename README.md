# Introduction to Deep-Learning 
> 이 자료는 MIT 강의 영상을 기반으로 작성되었으며, 공부 기록을 목적으로 두고 있습니다.
> > 강의 주소: <http://introtodeeplearning.com/>
## 1. Why Deep-Learning
> * 오늘 날의 딥러닝은 이전보다 더 빠른 속도로 가속화 되고 있기 때문에 매우 중요합니다. 얼굴 이미지를 생성하고, 인식하는 것을 넘어 가상의 시뮬레이션 환경을 생성하여 자율주행 차량을 훈련시키고, 실제 차량에 배포하는 단계로 이어지고 있습니다.
> * 그렇다면 왜 지금 중요한 지, 몇 가지 이유가 있습니다.
> > 1. 첫 번째는 '<b>데이터</b>'입니다. 현재 우리 주변에 수많은 데이터가 널리 퍼져있습니다. 인공지능 모델은 데이터가 많으면 많을수록 정확하고 정교한 작업이 가능하기 때문입니다.
> > 2. 두 번째는 '<b>하드웨어의 발전</b>'입니다. 하드웨어의 발전으로 규모가 큰 작업을 무리없이 할 수 있기 때문입니다.
> > 3. 세 번째는 '<b>소프트웨어</b>'입니다. 텐서플로우와 같은 소프트웨어 플랫폼의 발전으로 인해 접근이 용이해졌기 때문입니다.
## 2. What is Deep-Learning
> * 딥러닝을 배우기에 앞서 몇 가지 용어를 설명하겠습니다.
> > * '지능'은 미래의 결정이나 현재 취하는 행동을 알리는 데 사용할 수 있도록 정보를 처리하는 능력이라고 볼 수 있는데, '<b>인공지능</b>'은 이 처리 정보를 정확하게 수행할 수 있는 알고리즘을 구축하는 능력을 말합니다.
> > * '<b>머신러닝</b>'은 인공지능의 한 분야로, 기계를 구축하거나 기계에 수행 방법을 가르치는 데 초점을 맞추고 있습니다.
> > * '<b>딥러닝</b>'은 데이터에서 특징을 추출할 수 있는 신경망을 구축하는 방법에 초점을 맞춘 머신러닝의 하위 집합입니다.
## 3. The Perceptron
> * 신경망 언어에서 단일 뉴런을 퍼셉트론이라고 합니다.
> >   
> > ![Perceptron](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/70f36222-5838-462f-b764-b683d81f4ebe)
> > 
> > X는 입력을 나타내며, W는 가중치를 말합니다. X1에 W1을 곱하고, X2에 W2를 곱하는 방법으로 Xm과 Wm까지의 모든 곱셈 결과를 편향(초록색 원)과 함께 더한 후 활성화함수를 통해 최종 출력을 생성합니다.

> > ***Activation Functions**
> >  
> > ![Activation Functions](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/7056445e-8451-45c1-8760-0c552544036f)
> > 
> > * 활성화 함수는 Sigmoid, Hyperbolic Tangent, ReLU 등 여러 유형의 함수가 있습니다.
> > * 활성화 함수의 요점은 데이터에 대해 비선형성을 도입하는 것입니다. 우리가 관심을 갖는 거의 모든 데이터는 비선형적이기 때문입니다.

> > **Example**
> > 
> > ![Example(1)](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/b3776841-8143-481e-9b7a-8d60884263fb)
> > 
> > * 가중치가 실제 값을 갖는다고 하였을 때 위에서 배운 공식에 대입해보겠습니다. W0값은 1이며 X와 W를 각각 계산한 식입니다.
> > 
> > ![Example(2)](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/e74ca507-f691-4475-86de-ebdbbae7f11b)
> > 
> > * 계산한 식은 다음과 같은 직선이 되며, 임의의 X값 -1과 2를 대입했을 때, g(-6) 값이 나오게 됩니다. 시그모이드 함수 계산식
> > ![스크린샷 2024-03-12 033310](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/3c5b6ab0-8d48-4b1c-a2c0-d4877ee51cd2) 에 대입하면, 0.002 근사치의 값을 얻게 됩니다.
## 4. From perceptrons to neural networks
> * 퍼셉트론이 작동하는 방식과 전달하는 방법에 결정 내리는 데 세 단계가 있습니다.
> > 1. dot product(내적)
> > 2. Bias(편향)
> > 3. Non-Linearity(비선형성)

신경망에 대해 이 프로세스를 계속 반복합니다.

> > ![스크린샷 2024-03-12 034956](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/2f69ea82-d4e7-45b0-b45a-e46336b51722)
> > * 편의를 위해 가중치와 편향을 표시하지 않겠습니다. 다층 퍼셉트론은 기존의 퍼셉트론에 각각의 출력에 입력되는 각각의 가중치 값을 계산하면 됩니다.

> > * 기본적인 구조의 신경망 Layer를 코드에서 설명하겠습니다.
> > ![스크린샷 2024-03-12 035822](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/e2365e9f-10cd-49e5-9224-777361339d21)
> > * self.w = self.add_weight((input_dim, output_dim)) 와 self.b = self.add_weight((1, output_dim))는 가중치와 편향을 정의합니다. 가중치에 입력 차원과 출력 차원의 갯수를 정의해주고, 편향은 입력 노드가 한 개이므로 1과 출력 차원 갯수를 정의해줍니다.
> > * 다음은 호출 함수 정의를 해주는데, 'tf.matmul()'은 행렬곱을 의미합니다. 입력 값과 가중치를 행렬곱을 통해 계산을 하고, 편향을 더하여 Z를 정의해줍니다. 마지막으로 출력은 시그모이드 함수를 통해 값을 return합니다.
> > 
> > * 실제로는 텐선플로우와 같은 라이브러리에서 함수를 호출만 하면 됩니다.

## 5. Loss functions
> * 손실함수는 내 신경망이 예측값과 실제 값의 손실(오차)이 있는지, 손실이 있다면 얼마나 있는 지 확인하기 위해 사용합니다. 손실함수에는 여러 종류가 있지만, 대표적인 세 가지만 소개하겠습니다.
> > **손실함수 종류**
> > * <b>Binary Cross-entropy</b> : 실제 레이블과 예측 레이블 간의 교차 엔트로피 손실을 계산하며, 보통 이진 분류에 사용되는 손실함수입니다. 이진 분류에 사용되기 때문에 시그모이드 함수와 같이 사용됩니다.
> > * <b>Categorical Cross-entropy</b> : 다중 분류일 경우 사용하는 손실함수입니다. 보통 다중 분류에 적합한 Softmax와 함께 사용되며, one-hot encoding(원-핫 인코딩)된 형태로 제공될 때 사용합니다.
> > * 예측한 값과 실제 값 사이의 평균 제곱 오차를 정의하는 평균 제곱 오차 Mean Squared Error(MSE)가 있습니다. 제곱을 하기 때문에 오차가 양수, 음수와 관계없이 누적 값을 뚜렷하게 제공합니다.


## 6. Training and gradient descent
> * 손실을 구하는 것 뿐 아니라, 손실을 줄여나가는 것이 목표이기 때문에 손실. 즉, 어떤 가중치 세트가 가능한 가장 작은 손실을 주는 지 찾는 것이 중요합니다.
> * 랜덤한 지점을 선택하고 손실함수를 이용하여 변화를 계산해가며 최소 지점을 찾는 과정을 반복하는 경사하강법이 있습니다.
> * 기울기는 각 지점에서 함수의 값이 낮아지는 방향을 가리키기 때문에 기울기를 구하여 최솟값을 찾을 수 있습니다.
> * 학습률과 기울기를 곱하여 가중치 값에서 빼주는 방법으로 계속해서 업데이트 해가며 손실이 적은 지점을 찾아나갑니다.
> * 이를 코드로 나타내면,
![스크린샷 2024-03-12 045321](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/36ba05a1-0523-49f6-a67f-16c5e9157a23)

## 7. Backpropagation
> * 역전파란, 예측값과 실제값의 차이인 오차를 계산하고 이것을 다시 역으로 전파하여 가중치를 조정하는 것입니다.
> * 입력층에서 출력층으로 이동하는 순방향 신경망은 여러 층에 존재하는 가중치들을 모두 하나하나 업데이트하여 많은 연산량과 메모리를 요구하기 때문에 역전파를 사용합니다.

> ![스크린샷 2024-03-12 052331](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/9b71a8a2-b749-4028-94ff-af3673eaa966)

## 8. Setting the learning rate
> * 학습률은 인공 신경망 모델이 학습을 진행할 때 각 가중치를 얼마나 업데이트할 지 결정합니다.
> * 학습률이 너무 작으면 학습이 오래 걸리며, 지역 최솟값(Local minimum)에 갇힐 수 있습니다.
