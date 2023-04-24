# Authentication System 2

<br>

## User 객체와 CUD
- 회원 가입
- 회원 탈퇴
- 회원정보 수정
- 비밀번호 변경

<br>

## 회원 가입
- user 객체를 create 하는 것

<br>

## UserCreationForm()
- 회원 가입을 위한 built-in ModelForm

<br>

## get_user_model()
- 현재 프로젝트에서 활성화된 사용자 모델(active user model)을 반환하는 함수

<br>

## User 모델을 직접 참조하지 않는 이유
- user 모델을 get_user_model()을 사용해 참조하면 커스텀 User 모델을 자동으로 반환해주기 때문
- Django는 user 클래스를 직접 참조하는 대신 get_user_model()을 사용해 참조해야 한다고 강조

<br>

## 회원 탈퇴
- User 객체를 Delete 하는 것

<br>

## 회원정보 수정
- User 객체를 Update 하는 것

<br>

## UserChangeForm()
- 회원 가입을 위한 built-in ModelForm

<br>

## UserChangeForm 사용 시 문제점
- 일반 사용자가 접근해서는 안 될 정보들(field)까지 모두 수정이 가능해짐
- admin 인터페이스에서 사용되는 ModelForm이기 때문
- 따라서 CustomUserChangeForm에서 접근 가능한 필드를 조정해야 함

<br>

## 비밀번호 변경 페이지
- django는 비밀번호 변경 페이지를 회원정보 수정 form에서 별도 주소로 안내

<br>

## PasswordChangeForm()
- 비밀번호 변경을 위한 built-in Form

<br>

## 암호 변경 시 세션 무효화
- 비밀번호가 변경되면 기존 세션과의 회원 인증 정보가 일치하지 않게 되어 버려 로그인 상태가 유지되지 못 함
- 비밀번호는 잘 변경되었으나 비밀번호가 변경 되면서 기존 세션과의 회원 인증 정보가 일치하지 않기 때문

<br>

## update_session_auth_hash(request, user)
- 암호 변경 시 세션 무효화 방지
- 암호가 변경되어도 로그아웃 되지 않도록 새로운 password의 session data로 기존 session을 업데이트

<br>

## is_authenticated
- 사용자가 인증 되었는지 여부를 알 수 있는 user model의 속성
- 모든 user 인스턴스에 대해 항상 True인 읽기 전용 속성이며, AnonymousUser에 대해서는 항상 False임

<br>

## login_required
- 인증된 사용자에 대해서만 view 함수를 실행시키는 데코레이터
- 로그인 하지 않은 사용자의 경우 /account/login/주소로 redirect 시킴

<br>

## 데코레이터(Decorator)
- 기존에 작성된 함수에 기능을 추가하고 싶을 때, 해당 함수를 수정하지 않고 기능만을 추가 해주는 함수

2023.04.05