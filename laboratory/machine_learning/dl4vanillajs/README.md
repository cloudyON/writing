# Javascript로 Deep-learning 맛보기

요즘 딥러닝 또는 머신러닝을 학습한다고 하면 의심의 여지도 없이 Python부터 시작해야 한다고 한다. 그리고 Tensorflow든 Keras든 pyTorch든 프레임워크를 사용하면 쉽게 머신러닝 혹은 딥러닝 애플리케이션을 만들 수 있다고 한다. 대부분의 경우 이런 의견이 옳다는 사실에는 동의한다. 머신러닝으로 구현해야 하는 것들을 빠르고 쉽게 만들수 있고, 문제가 생기더라도 웹서핑이든 커뮤니티 등을 통해 도움을 얻을 수도 있다. 

하지만 이 글의 시작은 '왜 Python이 아니면 안되지?', '꼭 프레임워크를 써야만 하는걸까?' 라는 삐딱한 시각에서 시작했다. 그래서 쉽게 접근할 수 있는 스크립트 언어를 찾았고, 여차하면 웹브라우저 위에서 동작시켜볼 수도 있겟다는 생각에 Javascript로 만들어 보기로했다. 물론 프레임워크의 도움 없이, 필요한 기능이 있다면 모두 직접 구현해 가면서 언어 기본기능만 가지고 Deep-learning 모델을 작성할 것이다. 그리고 (성능을 보장 할 수는 없지만) 간단한 예제에 대해 모델을 학습하고 평가하는 과정을 소개하고자 한다.


## 1. 시작하며

들어가기 앞서 미리 밝혀두자면, 이 글은 개발가이드 또는 업무적용사례와 같은 거창한 글이 아니다. 그렇다고 해서 CNN/RNN이나 등의 제법 유명한 인공신경망을 구현해 보자는 것 또한 아니다. 이 글에서는 먼저 단순한 수준의 MLP(Multi-Layer Perceptron)을 이용한 모델을 작성하고, 샘플 프로젝트를 통해 훈련 및 평가를 하는 것을 목표로 할 것이다. 아주 거창한 개발동기와 소박한 개발목표로 시작한 작은 프로젝트지만, 스크립트 언어 하나만 가지고 Deep-learning 애플리케이션을 만들어보겟다는 용기와 패기가 가득한 도전기이자 기행문 정도로 가볍게 바라봐 줬으면 좋겠다.

앞으로 작성한 소스코드와 예제코드는 아래 Github 링크에서 볼 수 있다.

* **[dl4vanilla.js](https://github.com/ivorycirrus/dl4vanillajs)** : Javascript로 작성한 행렬연산 및 인공신경망(ANN) 작성 유틸리티
* **[dl4vanilla.js 예제](https://github.com/ivorycirrus/dl4vanillajs-node-example)** : Node.js로 실행 할 수 있는 다층퍼셉트론(MLP) 예제.