
## Transfer Learning & Fine tuning
![image](https://user-images.githubusercontent.com/61492320/206634499-c5399e4d-4c60-4feb-a630-239d5ac66829.png)


#### 나는 호랑이/표범을 분류햐고자함
- 개/고양이 분류하는 pretrained 모델을 갖고 있음

- 이미 잘 학습된 pretrained 모델을 활용해 새로운 데이터셋을 학습하는 과정이 "Transfer learning"

#### 이번엔 모든 포유류를 분류하고 싶음! 

- 얻고자하는 결과값이 다르기 때문에(output node 개수 다르기 때문) </br>

- 기존의 output layer를 삭제하고 새로운 layer를 붙여 사용함. 그리고 모델 다시 훈련시키는 것 "fine tuning"

![image](https://user-images.githubusercontent.com/61492320/206634521-46f0a20c-e849-437e-8fce-f121f2d25388.png)



## Pooling
### Pooling 사용하는 이유
앞선 layer들(CONV layer, Activation, etc... )을 거치고 나서 나온 output feature map의 모든 값이 필요한 것은 아니기 때문
### Pooling 효과
1. 파라미터가 줄기 때문에 Overfitting 억제
2. 계산량 줄이고, 속도 up

### Pooling 특징
- 학습해야할 파라미터 x (Max/avg/min)
- channel수는 그대로 유지
- input feature map에 변화(shift)가 있어도 pooling 결과에 대한 변화는 적다

