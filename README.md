# ZSL : Grounding DINO 🦖
## 개요
**Zero-Shot Learning**이란? **모델이 학습된 적 없는 클래스나 개념에 대해 추론할 수 있도록 하는 머신러닝 기술**이다. 주로, 비전-언어 모델에서 많이 사용되고, 핵심은 모델이 훈련되지 않은 상태에서도 새로운 클래스나 개념을 인식하고 이해할 수 있는 능력이다. <br>

멀티모달(Multimodal) AI에 관심을 갖고 리서치하던 중, Zero Shot Learning에 대해 알게되었고, 그 중 실시간 객체 인식에 강한 Grounding DINO를 테스트해보기로 했다. ```grounding_dino.ipynb```는 Grounding DINO를 이용하여 흉기난동을 감지하는 코드이며, 추후에 실시간 스트림에 연결하여 테스트해 볼 예정이다. 

## Grounding DINO ?
객체 감지와 관련된 ZSL을 위한 모델이다. DINO는 "Ditection Transformer"의 약자로, 트랜스포머 아키텍처를 이용하여 객체 감지를 수행한다. <br>
1. 텍스트(text) 기반으로 이미지(vision) 속에서 객체를 탐지할 수 있다.
2. Zero-Shot Learning 모델로 사전 학습된 클래스 외의 새로운 객체도 인식할 수 있다.
3. Swin Transformer-B 백본을 사용하여 높은 성능과 정확성을 보장한다.
4. 추가적인 학습 데이터가 없어도 새로운 객체를 인식할 수 있어, 데이터 수집과 라벨링에 드는 시간을 줄일 수 있다.
* 백본(backbone) : 최근 detector는 백본과 헤드의 두 부분으로 구성된다. 그 중 백본은 입력 이미지를 feature map으로 변형시켜주는 부분이다.

## Output
"A person with a deadly weapon in their hand" 이라는 텍스트를 넣어 Inference한 결과, 이미지에서 흉기를 들고 있는 사람을 잘 인식하였다. <br> 
비디오 객체 인식은 데이터의 많은 부분이 모자이크 처리되어 Inference를 진행하지 못했다. <br> 
![image](https://github.com/kingodjerry/grounding_dino/assets/143167244/64dc4ce1-7633-4814-89c6-37b04f8afcfe)
