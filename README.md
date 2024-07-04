## Deeplearning_teamproject

# "Railway track condition recognition using deep learning."
팀원 : 최지웅, 박선영, 윤혜상, 김연수


# 1. 주제 선정 이유
![image](https://github.com/chlwldnd542/Deeplearning_teamproject/assets/70998377/d322a864-90e2-4717-b227-ddeef0e4bb2b)

22년 11월, 80명의 부상자를 낸 영등포역 무궁화호 탈선 사고의 원인이 선로 분기부의 텅레일의 파손으로 밝혀졌다. 이처럼 부품 결함은 수많은 부상자가 발생하는 사고로 이어질 수 있다. 철도 불량 및 노화로 인한 운행 장애는 현재에도 높은 비율로 발생하고 있다.

[2024년 철도사고 및 운행장애 현황 월간보고(3월)] 에 따르면 2024년 1월부터 3월까지 일반철도와 도시철도에서 발생한 29건의 운행장애 중 12건, 약 41%가 부품 불량/노후로 인한 것으로 통계되었다. 이러한 사고 및 장애를 사전에 방지하기 위해서는 철도 선로의 부식 여부를 주기적으로 확인하여야 한다. 이에 수천 km 길이의 선로를 사람이 직접 다 점검하기보다 ai 딥러닝을 활용한다면 훨씬 효율적으로 점검이 가능할 것이라 판단이 되어 "Railway track condition recognition using deep learning”이라는 주제를 선정하게 되었다.

# 2. 데이터 선정
해당 프로젝트에서는 AIHUB의 ‘철도 선로 상태 인식 데이터’를 사용하였다. 해당 데이터는 일반 철도의 선로를 영상카메라 및 각종 특수장비를 활용하여 촬영한 이미지에 선로의 정상/이상이 라벨링 되어있는 데이터 셋이다. 레일의 편마모, 파상마모, 절손(훼손), 텅레일, 크로싱 절손 및 훼손 등 다양한 상태의 이상 레일 이미지로 구성되어 있다. 데이터 구성은 다음 표와 같다.
![image](https://github.com/chlwldnd542/Deeplearning_teamproject/assets/70998377/5c0c7e10-9d82-4d5a-81ff-4c4d9d08cf7f)

AIHUB 데이터 :
https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&dataSetSn=71391



