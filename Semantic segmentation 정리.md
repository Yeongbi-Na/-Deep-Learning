## Semantic segmentation?
![image](https://user-images.githubusercontent.com/61492320/206649803-ef5c565e-b351-4152-8e32-4ad01b0a449b.png)
#### '픽셀단위로 각 픽셀이 어떤 클래스에 속하는지' 분류하는 문제

</br>

## Metric
- pixel accuracy: (class 맞춘 개수)/ (전체 픽셀)
- mIoU : (Area of overlap)/(Area of Union)
- frequency weighted IU: IU 계산 시 각 예측한 클래스에 대한 픽셀 개수에 따라 가중치를 주고 싶을 때 하는 방법

</br>


## Semantic segmentation에서 receptive field
- semantic segmentation에서 높은 성능을 내기 위해서는, 최종 output feature map의 각 픽셀이 입력값에서 어느 크기의 영역을 커버할 수 있는지를 결정하는 receptive field 크기가 중요하게 작용
- 이때, Atrous convolution을 활용하면 파라미터 수를 늘리지 않으면서도 receptive field를 크게 키울 수 있기 때문에, DeepLab series에서는 이를 적극적으로 활용하려 노력


</br>


## Atrous Convolution
![image](https://user-images.githubusercontent.com/61492320/206650383-50c01a2d-7f72-4fc3-bac8-cf8f5fb8f4c8.png)
- (효과) 파라미터를 늘리지 않고도 더 넓은 receptive  field를 가질 수 있기에 deep한 네트워크에서도 spatial 정보 유지 가능
- semantic segmentation의 경우 dense prediction(조밀한 예측)이 필요한데, 이를 해결하기 위해 pooling layer를 없애고 atrous conv를 이용하면 receptive field를 확장시키고, spatial 정보를 유지
- ** dilation rate 커지면? 더 넓은 receptive field를 갖지만 zero padding이 아닌 유효한 영역이 줄어들어 weight 수도 줄어들 수 있음

</br>

## SPP(Spatial pyramid Pooling)
![image](https://user-images.githubusercontent.com/61492320/206654406-d42a628b-8e3f-4e71-8458-d38ebdf8556c.png)
- 하나의 input을 4x4, 2x2, 1x1 의 영역으로 나눔 -> 3개의 피라미드 생성
- 각각에 대해 Pooling을 수행하고 1x1 conv로 채널 수 조정
- 다시 featuremap 크기에 맞도록 upsampling
- (효과) 

</br>

## ASPP(Atrous conv + SPP)
- 다른 dilation rate를 가진 atrous pooling layer를 중첩하여 다양한 receptive field를 볼 수 있도록 적용
- Deeplab-v3에서 사용된 ASPP의 구조(b)
![image](https://user-images.githubusercontent.com/61492320/206652242-d913f229-0a58-4347-8338-0aae8125d1eb.png)


</br>


## Depthwise separable convolution
depthwise convolution을 진행한 후, pointwise convolution(1 x 1 convolution)을 진행
![image](https://user-images.githubusercontent.com/61492320/206652923-8be28234-101c-4fb8-8720-de0791148c55.png)
![image](https://user-images.githubusercontent.com/61492320/206653065-215ef2bd-464e-441d-8160-73ec96722c98.png)







이미지 출처:http://machinelearningkorea.com/2019/07/13/%EC%9D%B4%EB%AF%B8%EC%A7%80%EB%B3%84-%EB%B6%84%EB%A5%98%EB%AC%B8%EC%A0%9C/
