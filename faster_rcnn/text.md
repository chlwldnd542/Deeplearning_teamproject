R-CNN이란 regions with CNN으로, "Rich feature hierarchies for accurate object detection and semantic segmentaion(2013)"에서 처음 소개되어 딥러닝 기반의 object detection의 시작을 열었다. 이후 2015년 R-CNN의 단점을 보안한 fast R-CNN 모델이 공개되었고, 동일한 연도에 fast R-CNN의 한계점을 보안한 faster R-CNN이 공개되었다.
<center>
  <img src="https://drive.google.com/uc?id=1ILYPtaRMtyRqTc0q1pqTm_M_zaJHAsFD" width="500">
</center>

*   R-CNN
<center>
  <img src="https://drive.google.com/uc?id=1IgyyY0a5cldbK6Rz9x7LMkQOXhPetrFG" width="500">
</center>  

  1.   selective search를 통해 물체가 존재할 것 같은 지역을 2000개 정도 추출한다
  (*selective search: 유사도가 높은 pixel들을 점차 병합하여 여러 후보 영역을 생성)   

  2.   각각을 동일한 크기로 resize한 후, 미리 학습된 CNN 모델을 사용하여 feature vector를 추출한다.  

  3.   추출된 feature vector를 SVM classifier통해 class를 분류하고, Bounding Box Regression통해 박스의 위치를 교정한다.  

  R-CNN은 selective search을 통해 추출된 2000개 정도의 이미지를 각각 CNN 모델로 모두 처리하기 때문에 이 과정에서 병목현상이 일어난다. fast R-CNN은 다음과 같은 과정으로 이 한계점을 보안하였다.
  


---


*   Fast R-CNN
<center>
  <img src="https://drive.google.com/uc?id=1tTPqDkliPZ4cZtOyW9473J8VcjbYZAUo" width="500">
</center>  

  1.   미리 학습된 CNN을 통해 전체 이미지의 feature map을 생성한다.  

  2.   selective search를 통해서 찾은 각각의 RoI(Region of Interest)에 대하여 RoI Pooling을 진행하여 고정된 크기의 feature vector를 추출한다.  
  (*RoI Pooling: RoI를 동일한 크기로 max pooling하는 것)  

  3.   feature vector는 fully connected layer들을 통과한 뒤, softmax를 통해 class를 분류하고, Bounding Box Regression통해 박스의 위치를 교정한다.  

  Fast R-CNN은 CNN 모델을 한번만 통과시켜 R-CNN에서의 병목현상을 극복하였다. 하지만 여전히 selective search을 사용하여 해당 과정에서의 느린 연산 속도와 학습이 안되어 성능개선이 어렵다는 단점을 해결하지 못하였다.
  이를 보안하여 등장한 모델이 해당 프로젝트에서 사용할 Faster R-CNN이다.  


  *   R-CNN
<center>
  <img src="https://drive.google.com/uc?id=1IgyyY0a5cldbK6Rz9x7LMkQOXhPetrFG" width="500">
</center>  

  1.   selective search를 통해 물체가 존재할 것 같은 지역을 2000개 정도 추출한다.
  (*selective search: 유사도가 높은 pixel들을 점차 병합하여 여러 후보 영역을 생성)   

  2.   각각을 동일한 크기로 resize한 후, 미리 학습된 CNN 모델을 사용하여 feature vector를 추출한다.  

  3.   추출된 feature vector를 SVM classifier통해 class를 분류하고, Bounding Box Regression통해 박스의 위치를 교정한다.  

  R-CNN은 selective search을 통해 추출된 2000개 정도의 이미지를 각각 CNN 모델로 모두 처리하기 때문에 이 과정에서 병목현상이 일어난다. fast R-CNN은 다음과 같은 과정으로 이 한계점을 보안하였다.
  


---


*   Fast R-CNN
<center>
  <img src="https://drive.google.com/uc?id=1tTPqDkliPZ4cZtOyW9473J8VcjbYZAUo" width="500">
</center>  

  1.   미리 학습된 CNN을 통해 전체 이미지의 feature map을 생성한다.  

  2.   selective search를 통해서 찾은 각각의 RoI(Region of Interest)에 대하여 RoI Pooling을 진행하여 고정된 크기의 feature vector를 추출한다.  
  (*RoI Pooling: RoI를 동일한 크기로 max pooling하는 것)  

  3.   feature vector는 fully connected layer들을 통과한 뒤, softmax를 통해 class를 분류하고, Bounding Box Regression통해 박스의 위치를 교정한다.  

  Fast R-CNN은 CNN 모델을 한번만 통과시켜 R-CNN에서의 병목현상을 극복하였다. 하지만 여전히 selective search을 사용하여 해당 과정에서의 느린 연산 속도와 학습이 안되어 성능개선이 어렵다는 단점을 해결하지 못하였다.
  이를 보안하여 등장한 모델이 해당 프로젝트에서 사용할 Faster R-CNN이다.  


  <center>
  <img src="https://drive.google.com/uc?id=12gO5tJYajHGfcW-CeUhg_FUkqMAG-_kZ" width="400">
</center>  

  1.   미리 학습된 CNN을 통해 전체 이미지의 feature map을 생성한다.  

  2.   RPN(region proposal network)를 통해서 찾은 각각의 RoI에 대하여 RoI Pooling을 진행하여 고정된 크기의 feature vector를 추출한다.

  3.   feature vector는 fully connected layer들을 통과한 뒤, softmax를 통해 class를 분류하고, Bounding Box Regression통해 박스의 위치를 교정한다.

  Faster R-CNN은 selective search가 아닌 RPN 사용하였다는 점을 제외하고, 나머지 단계는 fast R-CNN과 동일하다.
  <center>
  <img src="https://drive.google.com/uc?id=1Ek0xp3BYSVlaJBS8XqwlfzUSTmhLqpgq" width="400">
  </center>   
  Faster R-CNN에서 사용한 RPN은 anchor로 지정된 지점에서 다양한 모양의 anchor box를 통해 각 anchor box에 물체의 존재 여부만을 판단하고, 박스의 위치를 조정한다.  

  RPN을 사용하므로써 연산 속도가 빨라지고, end-to-end 방식으로 학습 가능(output에서 input까지 bsckprop으로 계산 가능)하다.


  
이번 프로젝트에서는 Faster R-CNN을 사용하여 총 4개의 선로의 부품을 분류하는 모델을 구현하고자 한다. PyTorch에서 제공하는 pretraining된 Faster R-CNN을 불러와서 프로젝트에 사용할 데이터에 맞게 classifier 부분을 수정하여 사용하였다.
