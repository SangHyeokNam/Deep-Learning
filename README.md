# Introduction to Deep-Learning 
> 이 자료는 MIT 강의 영상을 기반으로 작성되었으며, 공부 기록을 목적으로 두고 있습니다.
> > 강의 주소: <http://introtodeeplearning.com/>
## 1. Why Deep-Learning
* 오늘 날의 딥러닝은 이전보다 더 빠른 속도로 가속화 되고 있기 때문에 매우 중요합니다. 얼굴 이미지를 생성하고, 인식하는 것을 넘어 가상의 시뮬레이션 환경을 생성하여 자율주행 차량을 훈련시키고, 실제 차량에 배포하는 단계로 이어지고 있습니다.
* 그렇다면 왜 지금 중요한 지, 몇 가지 이유가 있습니다.
> 1. 첫 번째는 '<b>데이터</b>'입니다. 현재 우리 주변에 수많은 데이터가 널리 퍼져있습니다. 인공지능 모델은 데이터가 많으면 많을수록 정확하고 정교한 작업이 가능하기 때문입니다.
> 2. 두 번째는 '<b>하드웨어의 발전</b>'입니다. 하드웨어의 발전으로 규모가 큰 작업을 무리없이 할 수 있기 때문입니다.
> 3. 세 번째는 '<b>소프트웨어</b>'입니다. 텐서플로우와 같은 소프트웨어 플랫폼의 발전으로 인해 접근이 용이해졌기 때문입니다.
## 2. What is Deep-Learning
* 딥러닝을 배우기에 앞서 몇 가지 용어를 설명하겠습니다.
> * '지능'은 미래의 결정이나 현재 취하는 행동을 알리는 데 사용할 수 있도록 정보를 처리하는 능력이라고 볼 수 있는데, '<b>인공지능</b>'은 이 처리 정보를 정확하게 수행할 수 있는 알고리즘을 구축하는 능력을 말합니다.
> * '<b>머신러닝</b>'은 인공지능의 한 분야로, 기계를 구축하거나 기계에 수행 방법을 가르치는 데 초점을 맞추고 있습니다.
> * '<b>딥러닝</b>'은 데이터에서 특징을 추출할 수 있는 신경망을 구축하는 방법에 초점을 맞춘 머신러닝의 하위 집합입니다.
## 3. The Perceptron
* 신경망 언어에서 단일 뉴런을 퍼셉트론이라고 합니다.
>  
> ![Perceptron](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/70f36222-5838-462f-b764-b683d81f4ebe)
>
> X는 입력을 나타내며, W는 가중치를 말합니다. X1에 W1을 곱하고, X2에 W2를 곱하는 방법으로 Xm과 Wm까지의 모든 곱셈 결과를 편향(초록색 원)과 함께 더한 후 활성화함수를 통해 최종 출력을 생성합니다.

> ***Activation Functions**
> 
> ![Activation Functions](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/7056445e-8451-45c1-8760-0c552544036f)
> 
> * 활성화 함수는 Sigmoid, Hyperbolic Tangent, ReLU 등 여러 유형의 함수가 있습니다.
> * 활성화 함수의 요점은 데이터에 대해 비선형성을 도입하는 것입니다. 우리가 관심을 갖는 거의 모든 데이터는 비선형적이기 때문입니다.

> **Example**
> 
> ![Example(1)](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/b3776841-8143-481e-9b7a-8d60884263fb)
>
> * 가중치가 실제 값을 갖는다고 하였을 때 위에서 배운 공식에 대입해보겠습니다. W0값은 1이며 X와 W를 각각 계산한 식입니다.
>
> ![Example(2)](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/e74ca507-f691-4475-86de-ebdbbae7f11b)
>
> * 계산한 식은 다음과 같은 직선이 되며, 임의의 X값 -1과 2를 대입했을 때, g(-6) 값이 나오게 됩니다.
> <img src="[/path/to/img.jpg](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/3c5b6ab0-8d48-4b1c-a2c0-d4877ee51cd2)https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/3c5b6ab0-8d48-4b1c-a2c0-d4877ee51cd2" width="450px" height="300px"</img>

