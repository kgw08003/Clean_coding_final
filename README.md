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
![클린컬리](https://github.com/user-attachments/assets/bd02c593-fa10-48bb-979d-a24f744183ea)


### 📃 구현 기능📃 

#### 김혜지
- [`ERD` 내 `ORDERS` `CARTS` 기능 담당]
- 장바구니 기능 (추가, 수정, 삭제)
- 물건구매
 ![image](https://github.com/user-attachments/assets/ed41cf67-889d-4b0b-b627-c8200ace2cbb)
 ![image](https://github.com/user-attachments/assets/195cc85e-a542-455c-b352-1e509268a252)
 ![image](https://github.com/user-attachments/assets/56935614-85f0-406c-926a-65464457e190)

#### 신덕근
- [`ERD` 내 `REVIEWS` 기능 담당]
- 상품 리뷰 작성, 수정, 삭제
 ![image](https://github.com/user-attachments/assets/90e46f61-5d60-4405-9fe5-f480564151e0)
 ![image](https://github.com/user-attachments/assets/f50d81d4-2887-4e5a-99f7-c34af2871507)


#### 김지웅
- [`ERD` 내 `USER` 기능 담당]
- 회원가입 및 유저 관련 내용 로그인 페이지
- 로그인, 회원가입
![image](https://github.com/user-attachments/assets/0e599038-ebb7-4f53-a9cf-77babee87063)
![image](https://github.com/user-attachments/assets/5c82ea31-0d02-46f7-ac5b-cee173fb1056)

- 비밀번호 재확인 페이지, 개인정보 페이지(`users` 내 비밀번호 재확인 페이지, 개인정보 페이지(유저정보 관련 내용)
![image](https://github.com/user-attachments/assets/f87e64ca-d6d7-4f37-a2b6-4a0e363e3de8)
![image](https://github.com/user-attachments/assets/3216e47e-51e1-437a-9877-36062881d80e)


#### 김향은
- [`ERD` 내 `PRODUCTS` 기능 담당]
- 판매할 물건 등록, 삭제, 수정
 ![image](https://github.com/user-attachments/assets/118953dc-762e-4785-ad8e-a1030b02dd01)



### 🔐 코드 작성하면서 어려웠던 기능🔐
### [김혜지]
###### 장바구니에 있는 상품을 주문으로 생성
- 문제점: 리뷰 기능과 합해지면서 오류가 발생: 리뷰에서는 로그인이 된 사용자, 물건을 구매한 사용자만이 리뷰를 작성할 수 있도록 구현하였으나 이점을 고려하지 않고 orders 기능을 구현하여 오류가 발생
- 해결 방법: 현재 요청을 보낸 사용자가 로그인이 된 상태인지 확인하기 위해 `order_create` 함수에 사용자 정보를 설정하는 `order.user = request.user` 코드를 추가

###  📝구현하려 했으나 해결하지 못한 기능📝
###### <담기> 버튼 기능
- 자바스크립트를 이용하면 쉽게 구현 가능한 기능
- 현재 상황:<담기> 버튼을 누르면 상품 상세페이지로 이동

### 🔥2차 프로젝트에서 구현하고 싶은 기능🔥
- 구매 이력 조회
- 메인 페이지에서 <담기> 버튼을 누르면 장바구니에 해당 상품이 담기게 하기
- <주문요청하기> 버튼을 누르면 배송상태가 `delivered`로 변경
- 찜하기 기능 추가

---------
### 🔐 코드 작성하면서 어려웠던 기능🔐
### [신덕근]
###### 리뷰 작성 가능한 상품 필터링
- 문제점: 주문, 상품, 다른 종류의 여러 데이터들을 한꺼번에 연결, 사용자가 주문한 상품, 배송상태, 리뷰 상태를 동시에 연결, 이미 리뷰를 작성한 상품은 제외하는 로직을 구현
- 해결 방법: Django orm 의 쿼리 사용 : 지정된 필드의 값만 가져오는 values_list 와 제외 기능인 exclude를 활용하여 데이터를 추출

###  📝구현하려 했으나 해결하지 못한 기능📝
###### 주문 시스템과의 미연동
- 현재 주문 시스템과의 자동 연동 기능이 구현되지 않아 admin에서 직접 주문상태를 delivered 로 설정해야 리뷰 작성 가능
###### 마이 페이지 -> 구매평
- 마이페이지 구매평 부분에 html, css문제로 클릭을 해야만 구매평(리뷰 관련 내용)이 표시됨

### 🔥2차 프로젝트에서 구현하고 싶은 기능🔥
- 주문 시스템과의 연동
- 리뷰 정렬 방식 개선(좋아요 기능 추가)
- 평균 별점 표시
- 마이페이지에서 리뷰 내용이 바로 보이도록 html과 css파일 재정리
- 신고기능
- 리뷰의 통계를 세분화하여 시각화(리뷰 작성률, 구매자 정보 통계 등을 이용)

--------
### 🔐 코드 작성하면서 어려웠던 기능🔐
### [김지웅]
###### 리뷰 작성 가능한 상품 필터링
- 문제점: 마이페이지를 들어가기 전, 비밀번호를 재확인하는 폼에서 아이디 입력란을 잠그고 싶었으나 에러가 발생
- 해결 방법:`readonly` 속성을 사용하여 입력 필드를 수정할 수 없게 만들었음. `readonly` 속성은 HTML의 `<input>` 요소에서 사용자가 값을 수정하지 못하도록 설정하는 속성으로, 보안과 사용자 편의성을 동시에 달성할 수 있었음.

###  📝구현하려 했으나 해결하지 못한 기능📝
###### 선물특가 타이머 기능
- 타이머 기능을 구현할 때, 한 번 설정한 시간은 수정이 불가능하여 새로 고침을 하면 타이머가 초기화됨.
- 현재 상황 : 새로고침 할 때마다 시간이 초기화되는 방식으로 설정됨


### 🔥2차 프로젝트에서 구현하고 싶은 기능🔥
- 개인 페이지에서 회원 정보 및 비밀번호 수정
- 추천인 코드 및 마일리지 기능
- 홈페이지 검색어 입력 기능 연동
- 선물특가 타이머 기능

----------
### 🔐 코드 작성하면서 어려웠던 기능🔐
### [김향은]
###### 리뷰 작성 가능한 상품 필터링
- 문제점: Category필드를 Product 모델에 추가하면서 기존에 등록된 Product 데이터와의 호환성 문제를 겪음, Produce 모델에 새로운 Catefory필드를 추가했지만, 기존에 저장된 제품 데이터에는 연결된 Category 객체가 없어 외래키 제약 조건을 위반하는 문제 발생
- 해결 방법: 기존 제품 데이터에 대해 기본 Category를 설정하고 새로운 Category 객체와 기존 데이터를 연결하는 마이그레이션 작업 수행

###  📝구현하려 했으나 해결하지 못한 기능📝
###### 구매 이력 조회 기능
- 기본적인 데이터 모델과 프로젝트 연결은 완료했으나 해당 데이터를 표시하는 방식에 여러 이슈가 발생
- 각 구매자의 주문 내역을 효율적으로 필터링하는 부분에서 문제 발생

### 🔥2차 프로젝트에서 구현하고 싶은 기능🔥
- 구매 이력 조회
- 날짜별 주문 내역 필터링
- 주문상태(배송중, 배송완료 등)에 따라 정렬
- 상품의 상세 페이지에서 좋아요 기능

------------

### 실행 방법 ⚙️
##### 패키지 설치
```  images파일 추가
python -m venv myweb
만들어진 폴더에 zip 파일내용 붙여넣기
cd myweb
./Scripts/activate
pip install django djangorestframework
pip install django_extensions pillow
또는 pip install -r requirements.txt 이용
python manage.py runserver
```
