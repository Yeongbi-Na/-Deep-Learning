
## Object Detection 논문 리뷰

논문 리뷰와 함께 논문을 읽으며 궁금했던 점들을 정리했습니다.</br>

논문 리뷰와 궁금한점에 대한 제 답은 논문 제목을 클릭하면 보실 수 있습니다.

### - [Yolo(You Only Look Once)](https://blog.naver.com/nybi123/222803345378) </br>
1. 왜 obj, noobj로 나누고 가중치를 부여했는가?
2.  BBox 생성시 제약사항은 없는지
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

## Object Detection 개념 정리
[What is Object Detection? compare with otehr algorithms](https://blog.naver.com/nybi123/222803349891)



## Semantic Segmentation 논문 리뷰

[FCN(fully connected network)](https://blog.naver.com/nybi123/222839521365)
