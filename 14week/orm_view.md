# ORM with view

<br/>

## HTTP request methods

<br/>

### redirect()
- 인자에 작성된 주소로 다시 요청을 보냄

<br/>

### HTTP 
- 네트워크 상에서 데이터를 주고 받기 위한 약속

<br/>

### HTTP request methods
- 데이터(리소스)에 어떤 요청(행동)을 원하는지 나타내는 것
- GET & POST

<br/>

### GET method
- 특정 리소스를 조회하는 요청
- GET으로 데이터를 전달하면 Query String 형식으로 보내짐

<br/>

### POST method
- 특정 리소스에 변경사항을 만드는 요청
- POST로 데이터를 전달하면 HTTP Body에 담겨 보내짐

<br/>

### HTTP response status code
- 특정 HTTP 요청이 성공적으로 완료되었는지 알려줌


<br/>

### 403 Forbidden
- 서버에 요청이 전달되었지만 권한 때문에 거절되었다는 것을 의미 

<br/>

### CSRF (Cross-site-request-forgery)
- 사용자가 자신의 의지와 무관하게 공격자가 의도한 행동을 하여 특정 웹 페이지를 보안에 취약하게 하거나 수정, 삭제 등의 작업을 하게 만드는 공격 방법

<br/>

### Security Token (CSRF Token)
- 대표적인 CSRF 방어 방법
1. 서버는 사용자 입력 데이터에 임의의 난수 값(token)을 부여
2. 매 요청마다 해당 token을 포함시켜 전송 시키도록 함
3. 이후 서버에서 요청을 받을 때마다 전달된 token이 유효한지 검증

<br/>

### POST Method는 데이터베이스에 대한 변경사항을 만드는 요청이기 때문에 토크을 사용해 최소한의 신원 확인을 하는 것

2023.03.30  