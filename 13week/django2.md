# Django

## Django project
- 애플리케이션의 집합
- DB 설정, URL 연결, 전체 앱 설정 등을 처리

<br/>

## Django application
- 독립적으로 작동하는 기능 단위 모듈
- 각자 특정한 기능을 담당하며 다른 앱들과 함께 하나의 프로젝트를 구성

<br/>

## 앱 생성
- python manage.py startapp articles

<br/>

## 앱 등록 
- 반드시 앱을 생성한 후에 등록해야 함
- 반대로 등록 후 생성은 불가능

<br/>

## 디자인 패턴
- 소프트웨어 설계에서 발생하는 문제를 해결하기 위한 일반적인 해결책
- 공통적인 문제를 해결하는데 쓰이는 형식화 된 관행

<br/>

## MVC 디자인 패턴 (Model-View-Controller)
- 애플리케이션을 구조화하는 대표적인 패턴
- 데이터, 사용자 인터페이스, 비즈니스 로직을 분리

<br/>

### __init__py
* 해당 폴더를 패지 인식하도록 설정

<br/>

### asgi.py
* 비동기식 

<br/>

### wsgi.py 
- 웹 서버와의 연결 관련 설정

<br/>

### manage.py
- Django 프로젝트와 다양한 방법으로 상호작용 하는 커멘드라인 유틸리티

<br/>

### admin.py 
- 관리자용 페이지 설정

<br/>

### models.py 
- DB와 관련된 Model을 정의
- MTV 패턴의 M

<br/>

### views.py 
- HTTP 요청을 처리하고 해당 요청에 대한 응답을 반환
- MTV 패턴의 V

<br/>

### apps.py
- 앱의 정보가 작성된 곳

<br/>

### tests.py
- 프로젝트 테스트 코드를 작성하는 곳

<br/>

## URLs
- https://128.0.0.1:8000/articles/ 로 요청이 왔을 때 view 모듈의 index 뷰 함수를 호출한다는 뜻

<br/>

## View
- 특정 경로에 있는 template과 request 객체를 결합해 응답 객체를 반환하는 index view 함수 정의

<br/>

## Template
- articles 앱 폴더안에 templates 폴더 작성
- templates 폴더 안에 템플릿 페이지 작성

<br/>

## 데이터 흐름에 따른 코드 작성
- URLs -> View -> Template

<br/>

## MTV 디자인 패턴 정리
- Model 
  - 데이터와 관련된 로직을 관리
  - 응용프로그램의 데이터 구조를 정의하고 데이터베이스의 기록을 관리
- Template
  - 레이아웃과 화면을 처리
  - 화면상의 사용자 인터페이스 구조와 레이아웃을 정의
- View
  - Model & Template과 관련한 로직을 처리해서 응답을 반환
  - 클라이언트의 요청에 대해 처리를 분기하는 역할
- View 예시
  - 데이터가 필요하다면 model에 접근해서 데이터를 가져오고 가져온 데이터를 template로 보내 화면을 구성하고 구성된 화면을 응답으로 만들어 클라이언트에게 반환

<br/>

## render 함수
- 주어진 템플릿을 주어진 컨텍스트 데이터와 결합하고 랜더링 된 텍스트와 함께 HttpResponse(응답) 객체를 반환하는 함수
1. request
  - 응답을 생성하는 데 사용되는 요청 객체
2. template_name
  - 템플릿 이름의 경로
3. context
  - 템플릿에서 사용할 데이터 (딕셔너리 타입으로 작성)
  
2023.03.21