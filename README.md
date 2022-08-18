
## Object Detection 논문 리뷰

논문 리뷰와 함께 논문을 읽으며 궁금했던 점들을 정리했습니다.</br>

논문 리뷰와 궁금한점에 대한 제 답은 논문 제목을 클릭하면 보실 수 있습니다.

### - [Yolo(You Only Look Once)](https://blog.naver.com/nybi123/222803345378) </br>
1. 왜 obj, noobj로 나누고 가중치를 부여했는가?
2.  BBox 생성시 제약사항은 없는지(최소 개수, 최소 grid size, 생성하는 Bbox의 범위 등)
3. 그리드 사이즈보다 작은 object도 잘 detection 하는지

### - [SSD(Single shot Detector)](https://blog.naver.com/nybi123)</br>
1. 왜 더 큰 receptive field가 필요한가?
2. smooth L1에서는 왜 [-1, 1] 구간에서 L2를 쓰고 L1을 쓰는가?
3. 만약 YOLO의 단점인 small size object detection에 대한 성능 측정을 하고자 한다면? (다양한 사이즈의 object를 가진 이미지이며 우리는 작은 사이즈 object에 대한 성능만 측정하고 싶다)
4. 왜 다양한 사이즈의 feature map을 사용?

### - [RCNN(Regions with CNN features)](https://blog.naver.com/nybi123/222816888626)</br>
1. 1-stage가 2-stage보다 빠른가, 진짜 더 빠른가?
2. sliding window는 large receptive field를 가짐, 이게 안좋은 건가?
3. 왜 classify에서 메모리 문제 해결 방법으로  standard hard negative mining method 쓰는지?
4. "실제 negative인데 맞추기 쉬운" 데이터 없이 맞추기 어려운 데이터만으로 모델을 학습시켜도 테스트 단계에서 잘 맞출 수 있을까?
5. 이 standard hard negative mining method 은 어떻게 구현하는지

### - [Fast R-CNN](https://blog.naver.com/nybi123/222824240300)</br>
1. scale invariance 가 필요한 이유
2. Fast RCNN에서 급격하게 속도가 빨라졌다. 그 이유는?
3. Fast RCNN은 기존 SVM 대신 softmax로 분류를 수행했다. softmax가 더 빠른가?


### - [Faster R-CNN](https://blog.naver.com/nybi123/222829407704)</br> 
1. training region proposal는 SS로 고정하고 test 는 RPN 으로 수행한 실험이 있음. 이렇게 해도 돠나? 타당한가?
2. 모든 과정을 GPU에서 수행할 수 있게 된 이유

</br>

## Semantic Segmentation 논문 리뷰

### - [FCN(fully connected network)](https://blog.naver.com/nybi123/222839521365)
1. 성능 비교 실험에서 R-CNN과 비교했는데 타당한 것인가?
2. kernal size가 1인 conv layer를 사용하는 이유, 장점

### - [U-net](https://blog.naver.com/nybi123/222845787585)
1. 이미지 데이터를 patch 단위로 나누어 사용하는 이유?
2. overlap 해서 패치 구성, overlap하지 않고 패치 구성 시 주의할점

### - [Encoder-Decoder  with  Atrous  Separable Convolution](https://blog.naver.com/nybi123/222851553250)
1. 왜 Receptive field가 큰 것이 좋은지
2. Atrous conv (dilated conv)가 sementic segmentation에서 더 좋은지?
3. objec boundaries에 대해 잘 예측한다와 같은 주장에 대한 실험 설계가 굉장히 까다로운 것 같다. detail이란 것이 주관적이기도 하고 이에 대한 마땅한 metrics가 없기 때문에 논문으로 제안된 모델을 사용할 때에도 이런 것들을 염두해두어야할 거 같다
</br>

## Object Detection 개념 정리
[What is Object Detection? compare with otehr algorithms](https://blog.naver.com/nybi123/222803349891)


