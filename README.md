# 🦁멋쟁이 사자처럼 쇼핑몰 구축 팀 프로젝트 🦁
###  🚀Clean_Curly 프로젝트 최종 🚀
- 마켓컬리 백엔드 클론코딩 프로젝트.
- 이커머스 사이트의 필수 기능을 구현


### 🚴개발 인원 및 기간
- [팀프로젝트 기간] 2024-10.16(수) ~ 2024-10.30(수)
- [개발인원] : 백엔드 4명

### 🛠️기술스택
- Language : `python3`
- Framework : `Django`



@@@@수정전@@@@


### 🤗 팀 멤버
- [신덕근](https://github.com/shindeokgeun)
- [김향은](https://github.com/myangeun)
- [김혜지](https://github.com/hjkim977)
- [김지웅](https://github.com/kgw08003)

### 홈페이지 데모
![마켓컬리](https://github.com/user-attachments/assets/39bfcab6-33c2-4c05-9ac5-1149e4fff9d8)



### 📃 구현 기능📃 

#### 김혜지
- [`ERD` 내 `ORDERS` `CARTS` 기능 담당]
- 장바구니 기능 (추가, 수정, 삭제)
- 물건구매


#### 신덕근
- [`ERD` 내 `REVIEWS` 기능 담당]
- 1차 개발 : 상품 리뷰의 기본적인 CRUD 기능 구현(리뷰 작성, 수정, 삭제 기능)
- 2차 개발 : 리뷰 시스템 고도화(추천 기능, 추천 수에 따른 리뷰 정렬 기능, 리뷰 신고 및 차단 기능)


#### 김지웅
- [`ERD` 내 `USER` 기능 담당]
- 1차 개발 : 메인 홈페이지 구성, 로그인, 로그아웃, 회원가입 및 유저 관련 내용 로그인 페이지, 개인 페이지
- 2차 개발 : 회원 정보 및 비밀번호 수정 (개인 페이지 내 추가), 적립금 및 마일리지 기능, Gmail SMTP 사용해서 아이디, 비밀번호 찾기 기능
소셜 로그인 (구글 OAuth 2.0을 활용한 로그인 기능), 선물특가 타이머 기능, 팝업창 추가 (메인홈페이지), 회원 탈퇴 기능 추가 (개인 페이지 내 추가)


#### 김향은
- [`ERD` 내 `PRODUCTS` 기능 담당]
- 1차 개발 : 관리페이지(admin)에서 판매할 물건 등록, 삭제 수정 기능 구현, 물건 상세 페이지 구현
- 2차 개발 : 카테고리별 상품 목록 페이지 구현, 마켓페이지(메인화면)에서 상품 슬라이더 기능 구현, 물건 상세 페이지에서 상품 수량에 따라 실시간으로 총 가격 알려주는 기능 추가, 
고객센터 -> 상품 관리 페이지 구현 (권한이 부여된 계정만 상품 등록,수정,삭제 가능/권한 없을 시 403 페이지로 이동), 고객센터 -> 구매자별 구매 이력 조회 페이지 구현(사용자, 상품명, 수량, 가격, 구매한 날짜)


### 🔐 코드 작성하면서 어려웠던 기능🔐
### [김혜지]
###### 장바구니에 있는 상품을 주문으로 생성
- 문제점: 
- 해결 방법: 

###  📝아쉬웠던 점📝
###### 

### 🔥느낀점🔥
- 

---------
### 🔐 코드 작성하면서 어려웠던 기능🔐
### [신덕근]
###### 동일 상품 재구매 시 리뷰 작성 불가
- 문제점: 동일 상품 재구매 시 리뷰 작성 불가(Product ID 기반의 단일 리뷰 제한), order_item과 리뷰 데이터 간 연결 부재로 인한 중복 데이터 발생
- 해결 방법:
- (1)모델 구조 개선
  Review 모델에 order_item 필드 추가: OneToOneField로 OrderItem과 연결
  각 리뷰가 특정 주문 건에 종속되도록 설계 변경
  
  (2)리뷰 작성 로직 개선
  검증 기준을 Product ID에서 OrderItem으로 변경
  배송 완료된 주문 건에 대한 리뷰 작성 가능하도록 수정
  
  (3)데이터 마이그레이션
  데이터 마이그레이션 파일 생성하여 기존 리뷰와 해당 주문 아이템 연결
  시점 기반 주문-리뷰 매칭 로직 구현

  구현 결과
  동일 상품 재구매 시에도 각 주문 건별로 독립적인 리뷰 작성 가능
  주문 - 리뷰 간 명확한 관계 수립

###  📝아쉬웠던 점📝
1. 기능 미구현
-관리자용 신고 처리 시스템
2. 신고 현황 관리
3. 신고 처리 결과 알림
-리뷰 통계 기능
4. 상세 평균 별점 표시
5. 심층 통계 데이터 제공

### 🔥느낀점🔥
설계의 중요성
- 2차 개발 당시 전반적인 설계로 비교적 빠른 진도와 3차 개발의 원활한 진행

코드 관리의 중요성
- 주석, 정리의 중요성을 느꼈습니다. 자신이 직접 만든 부분이라도 시간이 흐르면 수정할 때 주석 설명이 없는 부분은 다시 전체적으로 확인해야해서 꽤 시간이 지체 된 부분이 아쉬웠습니다.

협업 도구 활용
- Git을 사용해 작업의 효율성을 높여 협업에 대해서 조금 더 알게 되었던 시간이였습니다.

--------
### 🔐 코드 작성하면서 어려웠던 기능🔐
### [김지웅]
###### 소셜 로그인 기능에서 많은 어려움
문제점 : jango에서 소셜 로그인 설정을 했을 때 django의 기본 사용자 모델은 비밀번호를 필요로 하지 않기 때문에, 구글 계정으로 로그인하게 되면 django의 사용자 모델에 비밀번호가 저장되지 않는 경우가 생겼다. 
해결 방법 : 이를 해결하기 위해 찾아보다가 소셜 로그인 계정을 사용한 경우 해당 사용자들에게만 비밀번호를 설정하는 것을 만들면 되겠다 생각했고, 소셜 로그인 계정을 사용한 경우는 비밀번호가 None 처리 되어있늘 것을 확인하고, 이를 이용해서 비밀번호 설정 페이지를 만들어 개인페이지에서 비밀번호 인증전에 버튼을 만들어 이를 연동하여, 만약 비밀번호가 있는 사용자의 경우(정당한 회원절차에 의해 설정된 사람)은 해당 버튼 클릭시 403.html을 만들어 403오류페이지가 나오도록 유도함으로서 이를 해결함

###  📝아쉬웠던 점📝
###### 홈페이지 검색어 입력 기능 연동 , 쇼셜 로그인
- 홈페이지 상단에 검색어를 통해서 해당 상품 검색하는 기능을 추가해보고 싶었는데 개발 시간 부족으로 개발하지 못했습니다.
- 소셜 로그인의 경우 카카오 로그인을 제일 처음 시도하였는데, 카카오 로그인에서는 동의항목에서 개인정보 관련으로 카카오계정(이메일)
  account_email이 권한없음으로 나와서 해당 상황 때문에 문제가 발생했었다. 사업자 정보가 없는 상황에서는 개인 개발자 비즈앰전환이 필수인데
  비즈니스인증 받는 시간이 프로젝트 완료 기간을 넘어서 개인정보 동의 설정 권한 요청을 하지 못하였기에 이는 반영하지 않았다.
  네이버의 경우 계속 403에러의 늪에 빠져서 기간 내 개발을 포기하게 되었고 이에 구글 로그인 기능만 반영하여 홈페이지 제작을 하게 된 것입니다.


### 🔥느낀점🔥
- 2차 프로젝트에서는 github 를 활용하지 못했지만, 3차 프로젝트를 진행하면서 github의 중요성을 깊이 깨달았습니다. github를 통해 작업의 효율성을 높이고, 오류 발생 시 신속하게 대처할 수 있었던 것 같습니다.
  저번 프로젝트에서 느꼈던 소통의 문제 또한 코드 리뷰와 pull request 기능을 통해 팀원들 간의 소통이 보다 쉽게 이루어진 것 같습니다!
  또한 이번 클론코딩을 통해 실제 비즈니스 모델과 고객의 요구를 이해하는데 큰 도움이 되었으며, 다양한 기능을 직접 구현해 봄으로서 각 기능의 복잡성을 체감함과 동시에 django의 유용성에 대해서 다시한번 생각해 볼 수 있는 계기가 되었던 것 같습니다

----------
### 🔐 코드 작성하면서 어려웠던 기능🔐
### [김향은]
###### 메인 화면의 상품 슬라이더 기능
- 문제점: 한 페이지에 보여줄 상품 개수는 4개이지만 각 상품의 너비와 슬라이더 전체 너비에 따라 비율이 달라져 3개, 5개씩 보이는 에러가 발생함
- 해결 방법: 이를 해결하기 위해 상품의 이미지 크기와 각 간격을 더하여 상품의 너비를 구하고 슬라이더 전체 너비는 상품의 너비와 총 상품 개수를 곱한 값으로 설정하여
            슬라이더의 이동 범위를 계산하였음 계산된 값 만큼 슬라이더를 좌우로 이동하도록 하여 상품이 정확히 정렬되도록 함


###  📝아쉬웠던 점📝
###### 구매 이력 조회 기능
- 상품 입고 알림 기능을 추가하고 싶었으나 시간 관계상 완성해내지 못할 것 같아 시도하지 못했음

### 🔥느낀점🔥
- 생각보다 HTML,CSS 구현이 어려웠음. 백엔드 작업은 코드가 제대로 작동하는지 테스트 하기가 상대적으로 쉽지만
  프론트엔드는 시각적인 피드백이 필요하고 이를 확인하고 다시 수정하는 과정에서 어느 부분이 에러가 났는지 찾는게 어려웠음
  따라서 어떤 문제가 발생했는지 쉽게 알 수 있도록 HTTP 상태 코드를 사용하면 좋겠다고 느꼈고 앞으로의 협업에서 프론트엔드와 코드를 리뷰해보며 서로의 코드 흐름을 이해하는 것이 중요하다고 느낌

------------

### 실행 방법 ⚙️
##### 패키지 설치
```
git clone -b main https://github.com/kgw08003/Clean_coding_final.git myweb
python -m venv myweb
cd myweb
./Scripts/activate
pip install -r requirements.txt
python manage.py runserver
```
