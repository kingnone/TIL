# Authentication System

<br>

## Django Authentication System
- 사용자 인증과 관련된 기능을 모아 놓은 시스템
- 인증과 권한 부여를 함께 제공 및 처리

<br>

## Authentication
- 사용자가 자신이 누구인지 확인하는 것
- 신원 확인

<br>

## Authorization
- 인증된 사용자가 수행할 수 있는 작업을 결정
- 권한 부여


<br>

## 반드시 User 모델을 대체해야 할까?
- Django는 새 프로젝트를 시작하는 경우 비록 기본 user 모델이 충분 하더라도 커스텀 User 모델을 설정하는 것을 강력하게 권장(highly recommended)
- 커스텀 user 모델은 기본 user 모델과 동일하게 작동 하면서도 필요한 경우 나중에 맞춤 설정할 수 있기 때문
- 단 user 모델 대체 작업은 프로젝트의 모든 migrations 혹은 첫 migrate를 실행하기 전에 이 작업을 마쳐야 함

<br>

## Login
- session을 create하는 과정

<br>

## AuthenticationForm()
- 로그인을 위한 built-in form

<br>

## login(request, user)
- 인증된 사용자를 로그인 하는 함수

<br>

## get_user()
- AuthenticationForm의 인스턴스 메서드 유효성 검사를 통과했을 경우 로그인 한 사용자 객체를 반환

<br>

## Logout
- session을 delete하는 과정

<br>

## logouta(reqeust)
1. 현재 요청에 대한 session data를 DB에서 삭제
2. 클라이언트의 쿠키에서도 sessionid를 삭제

<br>

## context processors
- 템플릿이 렌더링 될 때 호출 가능한 컨텍스트 데이터 목록
- 작성된 컨텍스트 데이터는 기본적으로 템플릿에서 사용 가능한 변수로 포함된
- 즉 django에서 자주 사용하는 데이터 목록을 미리 템플릿에 로드 해 둔 것

<br>

## AbstractUser class
- 관리자 권한과 함께 완전한 기능을 가지고 있는 user model을 구현하는 추상 기본 클래스

<br>

## 유저 모델 대체하기 Tip
- 대체하는 과정을 외우기 어려울 경우 해당 공식문서를 보며 순서대로 진행하는 것을 권장

2023.04.04