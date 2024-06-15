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
- KIS Developer OpenApi 활용 : RESTful API, Web Socket
- ~배치 서비스인 AST_BATCH에서 매일 8:55AM 에 토큰 발급 요청 시, 발급된 토큰 캐싱 처리~

### 중심 기술
- Cloud : GCP (인스턴스 OS : Debian GNU/Linux 11)
- DB : MySQL 8.0
- Application : Spring Boot 3.2.0, JPA, WebClient, Java 17, Gradle 8.5
- Batch : Spring Batch 3.2.0, JPA, WebClient, Java 17, Gradle 8.5

### ERD
<img src="https://github.com/DevSpaceHub/portfolio/blob/main/AST%20DB%20ERD.png" width="1300" height="1200"/>

### AST-API

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
