# Django URLs

<br/>

## URL dispatcher
- URL 패턴을 정의하고 해당 패턴이 일치하는 요청을 처리할 view 함수를 연결 (매핑)

<br/>

## Variable Routing
- URL 일부에 변수를 포함시키는 것
- 변수는 view 함수의 인자로 전달 할 수 있음

<br/>

## Variable routing 작성법
```python
path('articles/<int:num>/', views.hello)
path('hello/<str:name>/', view.greeting)
```

<br/>

## Path converters
- URL 변수의 타입을 지정
- (str, int 등 5가지 타입 지원)

<br/>

## App URL mapping
- 각 앱에 URL을 정의하는 것
- 프로젝트와 각각의 앱이 URL을 나누어 관리하여 주소 관리를 편하게 하기 위함

<br/>

## include()
- 다른 URL들을 참조할 수 있도록 돕는 함수
- URL의 그 시점까지 일치하는 부분을 잘라내고, 남은 문자열 부분을 후속 처리를 위해 include된 URL로 전달

<br/>

## Naming URL patterns
- URL에 이름을 지정하는 것
- path 함수의 name 인자를 정의해서 사용

<br/>

## url tag
- 주어진 URL 패턴의 이름과 일치하는 절대 경로 주소를 반환

<br/>

## Trailing Slashes
- django는 URL 끝에 '/'가 없다면 자동으로 붙임
- django의 url 설계 철학
  - 기술적인 측면에서 foo.com/bar와 foo.com/bar/는 서로 다른 URL이다.
- 검색 엔진 로봇이나 웹 트래픽 분석 도구에서는 이 두 주소를 서로 다른 페이지로 봄
- django는 검색 엔진이 혼동하지 않게 하기 위해 사용
- 모든 프레임워크가 이렇게 동작하는 것은 아님

2023.03.23