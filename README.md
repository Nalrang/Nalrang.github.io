# Nalrang.github.io
## 금주 개발 진행 상황

개발 내용  
1. 로그인 화면

2. 로그인 세션 유지

3. 뷰-라우터로 네비게이션 기본 틀 잡기

4. MongoDB 세팅

5. nodejs - express 로 서버 구축  
  ( 실제 ) Client <-> Server <-> DB  
  ( 현재 ) Client <-> Server /////// Server <-> DB  
  


미진행 내용

DB 스키마 설계


## 특이사항

### 1. 클라이언트 -> 서버로 get 요청시 에러

![error-01](https://i.imgur.com/fge2PaD.png)

원인 : 서버측 보안사항으로 허가된 클라이언트만 접근 가능

해결 : 서버 app.js 소스에 코드 추가
```
app.use(function(req, res, next) {
  res.header('Access-Control-Allow-Origin', req.header('origin') );
  res.header('Access-Control-Allow-Credentials', true);
  res.header("Access-Control-Allow-Methods", "GET,HEAD,OPTIONS,POST,PUT");
  res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept, Authorization");
  next();
});
```
### 2. Vue 실행시 네트워크 IP 설정
로컬 개발 환경  
![error-02](https://i.imgur.com/QNdsdx9.png)

배포 서버 환경  
![error-03](https://i.imgur.com/r6WK3Op.png)


## 데모
<http://218.236.114.68:8080/main>

API 요청  
<http://218.236.114.68:6001/api/users>


## 바로 해야할 일
네비게이션 버튼 CSS 수정  
배포서버 IP 설정  
다음주 할 일 계획하고 실천하기  

