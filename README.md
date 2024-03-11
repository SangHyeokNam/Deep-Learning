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
> * 신경망 언어에서 단일 뉴런을 퍼셉트론이라고 합니다.
> ![Perceptron](https://github.com/SangHyeokNam/Deep-Learning/assets/149642144/14dc9097-3ffb-4224-b31c-e11fc52896db)
