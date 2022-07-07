## NMS(Non Maximum Suppression)
object detection에서 중복이 발생하는 BBox를 제거하기 위해 사용
비교대상은 주변 픽셀이 아닌 자신과 겹친 영역이 일정값 이상인 BBox
1. IoU값으로 proposals을 모두 정렬
2. RoI점수가 높은 propsal과 다른 proposals에 대해서 overlapping 비교
3. overlapping이 높은 것은 특정 threshold이상이면 지워버림(보통 threshold 0.6~0.9)
4. 위 과정을 반복하며 삭제
*Yolo연구원의 NMS 설명자료: https://docs.google.com/presentation/d/1aeRvtKG21KHdD5lg6Hgyhx5rPq_ZOsGjG5rJ1HP7BbA/pub?start=false&loop=false&delayms=3000&slide=id.g137784ab86_4_5544


</br>

## IoU(Intersection Over Union)
- jacard index라고도 하며 truth BBox와 pred BBox의 오버랩 비율을 정량화하기 위한 방법 *NMS에서는 2개의 pred BBox의 오버랩 비율을 계산
- 두 BBox가 겹쳐지는 영역이 넓다? 모델이 객체의 위치를 잘 추정했다는 의미
- IoU 임계값보다 작은 값을 갖는 BBox의 경우 negative로 간주


- IoU = (Target ∩ Prediction) / (Target U Prediction)  * 0 <= IoU <= 1

</br>

## 분류 성능지표
- Precision = (TP)/(TP+FP) True라고 예측한 것 중 맞힌 것 ex) 스팸메일 예측 실제로 F인 것을 T로 예측하면 안됨
- Recall = TP/(TP+FN) 실제값이 True 인것중 맞힌 것 ex) 암 검출, 금융사기
- F1 score = 2*(Precision + Recall)/(Precision + Recall)

</br>

## Object dectection에서의 성능지표
- Precision: 예측한 BBox들 중 클래스까지 정확히 예측한 비율
- Recall: 실제 Object들 중 박스를 제대로 친 비율
- TP: BBox, 클래스 모두 정확히 예측한 경우 (IoU >= 임계값)
- FP: 실제 object가 아닌데 BBox 생성 or 클래스 예측(IoU <= 임계값)
- FN: 실제 Object인데 BBox 생성하지 않은 개수
</br>

## Confidence와 BBox수
Confidence socre: 예측 BBox 내 존재하는 객체의 범주를 예측한 확률의 최대값, 즉 예측한 객체가 특정 범주에 속할 확률이 얼마나 확실한지를 나타내는 지표
- Confidence 임계값이 낮으면 BBox 수 증가
- Confidence 임계값이 높으면 BBox 수 감소




참고: https://herbwood.tistory.com/2, https://velog.io/@tataki26/%EC%98%A4%ED%94%88, https://www.waytoliah.com/1491
