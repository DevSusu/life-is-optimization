# life-is-optimization
> 2019-2학기 졸업프로젝트 수행 계획서

## 그래프 구성

### Graph Construction from Google Map

#### Node
* 위치
  * 위도/경도
  * 주소 (한글, 현지)
  * 영역을 나타낼 SHP (shape 정보)
* 영업시간 , 바쁜시간 , 쉬는시간 (Opening/Closing, Busy hours, Break time)
* 분류
  * 숙소, 주차장, 전망, 박물관, 음식점, ...
* 사진
* 전화번호
* 웹사이트
* 별점, 리뷰
* 질문 답변
  * 경복궁은 한복을 입으면 무료입장이 가능하다 와 같은 정형화하기 어려운 정보들
  * 와이파이를 제공하나요 등
* 소요시간 - 둘러보는데 걸리는 통상적인 시간

Google Map의 [Place API](https://developers.google.com/places/web-service/details)를 사용하면 될 것 같습니다.
https://developers.google.com/places/web-service/place-data-fields 위의 항목들에 대한 정보를 거의 제공합니다. 부족할 경우 Google Map 페이지를 약간 크롤링하는 방법도 있겠습니다.

#### Edge
* Node1, Node2
* 출발시간 혹은 도착시간
  * 해당 시간의 도로상황을 고려하기 위함
* 이동수단
  * 버스, 지하철, 트램 등의 대중교통
  * 도보
  * 자전거
  * 차량
  * 관광지가 근접해있다면, 걸어서 이동하고 두 관광지를 모두 본 이후에 렌트카에 탑승하는 등의 상황도 있을 것이라 생각했습니다.

Node와 마찬가지로 Google Map의 [Direction API](https://developers.google.com/maps/documentation/directions/intro)를 사용하면 될 것 같습니다.


## Optimization

### Object Function
* 짧은 이동시간

### Constraint
가장 주관적인 부분 같습니다. 서비스 상에서는 결국 사용자의 만족도가 가장 중요한데, 그 취향을 반영할 수 있는 방법을 생각해봐야겠습니다.
* 바쁘지 않은 시간대에 방문 / 꼭 들려야 하는 시간대 지정
* 꼭 들리고 싶은 관광지 고정
* 복귀시간


## 시각화
간단한 단일 웹 페이지를 만드는 방향을 생각중입니다.

### 기능
* 숙소 지정
* 하루 안에 방문하고자 하는 포인트 선택 (추천 시스템이 들어가면 이 과정도 대체될 수 있을듯합니다)
  * <img src="https://raw.githubusercontent.com/DevSusu/life-is-optimization/master/research/tripple-ui-selecting.jpeg" width="300px"/>
* 일정을 시작할 시간 선택
* 생성된 일정을 화면 우측에서는 지도로, 좌측에서는 순서로 보여주려 합니다
  * [https://triple.guide/intro/](https://triple.guide/intro/)와 비슷한 화면이 되지 않을까 합니다.
  * <img src="https://raw.githubusercontent.com/DevSusu/life-is-optimization/master/research/tripple-ui.jpg" width="300px"/>
* 생성된 일정을 Drag&Drop으로 순서 변경
  * 한 장소의 체류시간 조정
* 일정 삭제
* 새로운 일정, 쉬는시간 삽입
