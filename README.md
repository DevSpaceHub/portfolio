# portfolio
DevSpaceHub에서 진행되는 프로젝트들에 대한 포트폴리오 설명 Repository

# AST 프로젝트
### 자동 (AST : Awake (항상 깨어있는), Auto (자동화된)) 주식 (Stock) 매매 (Trade)

# 멤버
### 윤기범
### 역할 : 기획, Devops, Batch 개발
### 문윤지
### 역할 : 기획, API 개발

---
### 전체 구성도
<img src="https://github.com/DevSpaceHub/AST/assets/66311276/64b326e7-3063-4ec7-98fd-86453ea70d61" width="310" height="315"/>

### 중심 기능
- 매수/매도 알고리즘 로직에 따른 주문 처리
- 한국투자증권 OpenAPI (KIS Developer OpenApi) 활용 : RESTful API, Web Socket

### 중심 기술
- Cloud : GCP (인스턴스 OS : Debian GNU/Linux 11)
- DB : MySQL 8.0
- Application : Spring Boot 3.2.0, JPA, WebClient, Java 17, Gradle 8.5
- Batch : Spring Batch 3.2.0, JPA, WebClient, Java 17, Gradle 8.5

### ERD
<img src="https://github.com/DevSpaceHub/portfolio/blob/main/AST%20DB%20ERD.png" width="2000" height="600"/>

### AST-API
제공하는 거래소 : 한국, NASDAQ, NESD
제공 기능 :
1. 매수/매도 주문 - 기준 지표에 부합하는 종목에 대해 주문한다. (분할 매수 기능 O)
2. 알림 기능 - 발생하는 주요한 이벤트에 대해 디스코드 알림 메세지를 발송한다. (주문 결과, 체결 결과)
3. 예약 매수 주문 - 사용자가 원하는 기간, 원하는 주문가와 수량에 대해 저장하면, 목표 수량을 채우기까지 매수 주문이 매일 발생한다.

### AST-BATCH
#### scheduler
1. 접근토큰 발급
- 매일 6시간마다 실행
2. 매수 주문
- 평일 오전 9시 ~ 14시 4초마다 실행
3. 매도 주문
- 평일 오전 9시 ~ 14시 2초마다 실행
4. 체결결과 처리
- 평일 15시 31분 실행
5. 거래량순위
- 평일 오진 8시 ~ 15시 30분마다 실행
6. 배치 메타 테이블 삭제
- 매일 오전 0시 0분 실행
 

### Admin
https://ast-admin.selectfromuser.com
- 주문관리
   1. 주문
   2. 예약매수
- 토큰관리
- 종목관리
