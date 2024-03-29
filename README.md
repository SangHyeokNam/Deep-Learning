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
> > * '지능'은 미래의 결정이나 현재 취하는 행동을 알리는 데 사용할 수 있도록 정보를 처리하는 능력이라고 볼 수 있는데, '<b>인공지능</b>'은 컴퓨터가 사람의 사고와 행동, 지능을 모방하거나 구현할 수 있는 기술을 말합니다.
> > * '<b>머신러닝</b>'은 인공지능의 한 분야로, 컴퓨터가 데이터를 분석하고 주어진 패턴을 학습해 새로운 데이터에 대한 예측을 할 수 있게 하는 기술입니다.
> > * '<b>딥러닝</b>'은 데이터에서 특징을 추출할 수 있는 신경망을 구축하는 방법으로, 머신러닝의 하위 집합입니다.
> > * '<b>머신러닝</b>'은 특징 추출을 사람이 해야하지만, '<b>딥러닝</b>'은 특징을 자동으로 추출할 수 있다는 차이점이 있습니다.
## 3. The Perceptron
> * 딥러닝에서 단일 뉴런을 <b>퍼셉트론</b>이라고 합니다.
>   
> ![Perceptron](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/70f36222-5838-462f-b764-b683d81f4ebe)
> 
> X는 입력을 나타내며, W는 가중치를 말합니다. X1에 W1을 곱하고, X2에 W2를 곱하는 방법으로 Xm과 Wm까지의 모든 곱셈 결과를 편향(초록색 원)과 함께 더한 후 활성화함수를 통해 최종 출력을 생성합니다.

> ***Activation Functions**
>  
> ![Activation Functions](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/7056445e-8451-45c1-8760-0c552544036f)
>
> * 활성화 함수란, 입력을 받아서 활성화 또는 비활성화를 결정하는 데 사용되는 함수입니다.
> * 활성화 함수는 <b>Sigmoid, Hyperbolic Tangent, ReLU</b> 등 여러 비선형 함수가 있습니다.
> * 활성화 함수에서 비선형 함수를 쓰는 이유는 크게 두 가지가 있습니다. 첫 번째는 현실의 대부분의 문제는 비선형 문제이기 때문이고, 두 번째는 선형 함수는 하나의 Layer로 표현이 가능하기 때문에 층을 쌓는 의미가 없어지기 때문입니다.
> * 선형 함수가 왜 층을 쌓는 의미가 없는 지 알아보기 전에 선형, 비선형의 정의를 설명하자면,
>
> ![스크린샷 2024-03-14 170237](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/37739e7a-c07d-44e0-87e2-3552ab4eb011)
>
> * 위 사진이 선형에 대한 정의입니다. 비선형은 선형으로 정의되지 않는 모든 함수 의미하는데, 선형 함수가 층을 쌓는 의미가 없는 이유는 예를 들어 y=ax 라는 선형 함수가 있고 입력값이 3개의 Layer를 지난다고 했을 때 y=f(f(f(x)))이고, a(a(a(x)))여서 결과 값은 a³x 이므로 결국 세제곱 형태의 활성화 함수 하나로 표현이 가능합니다. 따라서 Layer가 3개인 신경망과 1개인 신경망의 차이가 없어지게 되며, 모델의 성능을 저하시키고 효율성이 떨어지기 때문에 비선형 함수를 사용합니다.
> * (질문) 1차 함수로 한 개의 직선이 만들어진 모든 것을 선형 함수라 하는 게 맞는 지, y=ax가 선형 함수이고, y=ax+b는 비선형인 지


> **Example**
> 
> ![Example(1)](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/b3776841-8143-481e-9b7a-8d60884263fb)
> 
> * 가중치가 실제 값을 갖는다고 하였을 때 위에서 배운 공식에 대입해보겠습니다. W0값은 1이며 X와 W를 각각 계산한 식입니다.
> * 여기서 T는 전치행렬을 뜻합니다. 전치행렬은 행렬의 행과 열을 바꾸어 얻어낸 행렬을 의미합니다.
> 
> ![Example(2)](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/e74ca507-f691-4475-86de-ebdbbae7f11b)
> 
> * 계산한 식은 다음과 같은 직선이 되며, 임의의 X값 -1과 2를 대입했을 때, g(-6) 값이 나오게 됩니다. 시그모이드 함수 계산식
> ![스크린샷 2024-03-12 033310](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/3c5b6ab0-8d48-4b1c-a2c0-d4877ee51cd2) 에 대입하면, 0.002 근사치의 값을 얻게 됩니다.
> * 아직 이 그림이 어떤 걸 의미하는 지 잘 모르겠습니다.

## 4. From perceptrons to neural networks
> * 퍼셉트론이 작동하는 방식과 전달하는 방법에 결정 내리는 데 세 단계가 있습니다.
> > 1. dot product(내적) (*내적은 두 개의 벡터가 존재할 때 한 벡터의 방향으로 나머지 하나를 projection(투영) 시킨 것과 다른 한 벡터의 크기의 곱으로, 결과값은 스칼라입니다.)
> > 2. Bias(편향)
> > 3. Non-Linearity(비선형성)

신경망에 대해 이 프로세스를 계속 반복합니다.

> * 퍼셉트론은 입력에 가중치를 곱해서 더한값, 입력과 가중치(W)들을 내적을 수행한 결과를 어떤 기준 보다 높으면 출력하고 아니면 출력하지않도록 동작합니다. 이 때 기준이 되는 함수가 활성화 함수입니다.

> ![스크린샷 2024-03-12 034956](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/2f69ea82-d4e7-45b0-b45a-e46336b51722)
> * 이 그림에서 내적은 ![스크린샷 2024-03-14 210757](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/743d6dd1-f447-47d7-9bc3-337a7c2911b4) 부분입니다.

> * 기본적인 구조의 신경망 Layer를 코드에서 설명하겠습니다.
> ![스크린샷 2024-03-12 035822](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/e2365e9f-10cd-49e5-9224-777361339d21)
> * self.w = self.add_weight((input_dim, output_dim)) 와 self.b = self.add_weight((1, output_dim))는 가중치와 편향을 정의합니다. 가중치에 입력 차원과 출력 차원의 갯수를 정의해주고, 편향은 입력 노드가 한 개이므로 1과 출력 차원 갯수를 정의해줍니다. 여기서 add_weight는 가중치를 생성하는 지름길을 제공하는 역할을 합니다.
> * 다음은 호출 함수 정의를 해주는데, 'tf.matmul()'은 행렬곱을 의미합니다. 입력 값과 가중치를 행렬곱을 통해 계산을 하고, 편향을 더하여 Z를 정의해줍니다. 마지막으로 출력은 시그모이드 함수를 통해 값을 return합니다.
> * 행렬곱을 사용하는 가장 큰 이유는 대부분의 프로그래밍 언어에서 복잡한 행렬 계산을 빠르고 정확하게 수행할 수 있기 때문입니다. 
>  
> * 실제로는 텐선플로우와 같은 라이브러리에서 함수를 호출만 하면 됩니다.

## 5. Loss functions
> * 손실함수는 내 신경망이 예측값과 실제 값의 손실(오차)이 있는지, 손실이 있다면 얼마나 있는 지 확인하기 위해 사용합니다. 손실함수에는 여러 종류가 있지만, 대표적인 세 가지만 소개하겠습니다.
> > **손실함수 종류**
> > * <b>Binary Cross-entropy</b> : 실제 레이블과 예측 레이블 간의 교차 엔트로피 손실을 계산하며, 보통 이진 분류에 사용되는 손실함수입니다. 이진 분류에 사용되기 때문에 시그모이드 함수와 같이 사용됩니다.
> > * <b>Categorical Cross-entropy</b> : 다중 분류일 경우 사용하는 손실함수입니다. 보통 다중 분류에 적합한 Softmax와 함께 사용되며, one-hot encoding(원-핫 인코딩)된 형태로 제공될 때 사용합니다.
> > * 예측한 값과 실제 값 사이의 평균 제곱 오차를 정의하는 평균 제곱 오차 <b>Mean Squared Error(MSE)</b>가 있습니다. 제곱을 하기 때문에 오차가 양수, 음수와 관계없이 누적 값을 뚜렷하게 제공합니다.
> * entropy : 정보의 불확실성이나 무질서도를 나타내는 수치로, 가능한 모든 상태에 대한 정보를 고려하여 그 상태가 발생할 확률에 따라 가중치를 더한 값입니다. 상황이 더 불확실하거나 무질서하다면 entropy 값은 높아지고, 반대로 상황이 더 확실하거나 질서 정연하다면 entropy 값은 낮아집니다.
> * Cross-entropy : 모델에서 예측한 확률값이 실제값과 비교했을 때 틀릴 수 있는 정보량을 의미하며, entropy가 정답이 나올 확률만을 대상으로 측정한 값이었다면 Cross-entropy는 모델에서 예측한 확률과 정답확률을 모두 사용해 측정한 값입니다.


## 6. Training and gradient descent
> * 손실을 구하는 것 뿐 아니라, 손실을 줄여나가는 것이 목표이기 때문에 손실. 즉, 어떤 가중치 세트가 가능한 가장 작은 손실을 주는 지 찾는 것이 중요합니다.
> * 랜덤한 지점을 선택하고 손실함수를 이용하여 변화를 계산해가며 최소 지점을 찾는 과정을 반복하는 경사하강법이 있습니다.
> * 기울기는 각 지점에서 함수의 방향을 가리키기 때문에 기울기를 구하여 최솟값을 찾을 수 있습니다.
> * 학습률과 기울기를 곱하여 가중치 값에서 빼주는 방법으로 계속해서 업데이트 해가며 손실이 적은 지점을 찾아나갑니다.

## 7. Backpropagation
> * <b>역전파</b>란, 예측값과 실제값의 차이인 오차를 계산하고 이것을 다시 역으로 전파하여 가중치를 조정하는 것입니다.
> * 입력층에서 출력층으로 이동하는 순방향 신경망은 여러 층에 존재하는 가중치들을 모두 하나하나 업데이트하여 많은 연산량과 메모리를 요구하기 때문에 역전파를 사용합니다.

> ![스크린샷 2024-03-12 052331](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/9b71a8a2-b749-4028-94ff-af3673eaa966)

## 8. Setting the learning rate
> * 학습률은 인공 신경망 모델이 학습을 진행할 때 각 가중치를 얼마나 업데이트할 지 결정합니다.
> * 학습률이 너무 작으면 학습이 오래 걸리며, <b>지역 최솟값(Local minimum)</b>에 갇힐 수 있습니다.
> * 학습률이 너무 크면 발산해버려 성능이 떨어지며 올바른 모델을 만들 수 없으므로 적절한 학습률을 설정하는 것이 중요합니다.
> * 적절한 학습률을 설정하기 위해 직접 대입해보며 수정하거나, 최적화 알고리즘을 이용합니다.
> * 최적화 알고리즘 '<b>Optimizer</b>'은 보통 '<b>Adam</b>'을 사용하는데, 진행하던 속도에 관성을 주고, 최근 경로의 곡면의 변화량에 따른 적응적 학습률을 가진 알고리즘입니다.

## 9. Batched gradient descent
> * 실제 전체 데이터는 크기가 너무 커서 기울기를 전부 계산하는 것은 불가능합니다. 데이터의 단일 예에 대해 기울기를 계산해야 합니다.
> > * <b>배치 경사 하강법(BGD)</b>은 손실 함수의 기울기 계산에 전체 학습 데이터셋의 크기와 동일하게 잡는 방법입니다. 각 반복마다 모든 훈련데이터 세트를 처리하기 때문에 지역 최소값(Local minimum)에 갇힐 가능성이 높습니다.
> > * <b>확률적 경사 하강법(SGD)</b>은 무작위 데이터를 선택하고 그 데이터에 대해 기울기를 계산하는 방법입니다. 계산 속도가 매우 빠르지만, 무작위 데이터를 선택하기 때문에 불안정합니다.
> > * <b>미니 배치 경사 하강법(MGD)</b>은 위 두 가지 방법의 장점을 가져온 방법입니다. 배치 크기를 줄이고, 확률적 경사 하강법을 사용하여 안정적입니다.

## 10. Regularization: dropout and early stopping
> * 확률적 경사하강법을 사용하여 신경망을 최적화할 때 훈련 데이터에만 치우치며 새로 주어진 데이터에 대한 성능이 떨어지는 현상인 <b>과적합</b> 문제가 발생합니다.
> * 과적합을 방지하기 위해 <b>정규화(Regularization)</b>를 합니다.
> > <b>Normalization, Regularization, standardization 모두 번역하면 정규화라고 합니다. 
Normalization은 값의 범위를 0~1 사이로 바꾸어 Local minima에 빠질 위험 감소, Regularization은 가중치를 조정하는데 제약을 걸어 Overfitting을 방지, standardization은 값의 범위를 평균 0, 분산 1이 되도록 변환하여 Local minima에 빠질 위험 감소</b>

> * 가장 널리 사용되는 정규화 기술은 <b>Dropout</b>이 있습니다.
> > Dropout과 함께 %값을 지정하여 해당 확률로 훈련의 여러 반복 중 뉴런을 무작위로 끄거나 켤 수 있습니다. 신경망의 경로 내에서 더 깊은 의미를 포착하도록 제어하며, 신경망의 용량을 크게 낮추고, 속도가 향상됩니다.
>
> * 또 다른 정규화 기술로 <b>Early Stopping</b>이 있습니다.
> >  훈련을 통해 손실을 줄여나가는 중 training set의 손실이 안정화되고 test set의 손실이 다시 증가하는 시점이 있습니다.
> > 이 때부터 과적합이 발생하며, 손실이 증가하기 직전의 지점이 가장 정확도가 높은 지점이기 때문에 early Stopping을 통해 학습을 중지 시킵니다. 이 시점 전에 중지 시키는 것도 과소적합 모델이 생성 되어 성능이 떨어집니다.

## 11. Summary
> * 핵심 사항을 요약하며 마무리 하겠습니다.
> > * 단일 뉴런인 퍼셉트론의 신경망 기본 구성 요소를 다루었으며,
> > * 이를 통해 다층 퍼셉트론 학습하는 방법을 배우고,
> > * 이를 다시 데이터 세트에 적용하여 역전파하는 방법을 배웠습니다.
> > * 추가적으로 정규화 하는 방법까지 배웠습니다.
