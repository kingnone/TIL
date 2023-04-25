# Django - Static files

<br>

## Static Files
- 서버 측에서 변경되지 않고 고정적으로 제공되는 파일
- 이미지, JS, CSS 파일 등

<br>

## 웹 서버와 정적 파일
- 웹 서버의 기본동작은
  - 특정 위치에 있는 자원을 요청 받아서
  - 응답을 처리하고 제공하는 것
- 이는 자원에 접근 가능한 주소가 있다는 의미
- 웹 서버는 요청 받은 URL로 서버에 존재하는 정적 자원을 제공함
- 결국 정적 파일을 제공하기 위한 경로가 있어야 함

<br>

## STATIC_URL
- 기본 경로 및 추가 경로에 위치한 정적 파일을 참조하기 위한 URL 실제 파일이나 디렉토리가 아니며, URL로만 존재

<br>

## STATICFILES_DIRS
- 정적 파일의 기본 경로 외에 추가적인 경로 목록을 정의하는 리스트

<br>

## Media Files
- 사용자가 웹에서 업로드하는 정적 파일 (user-uploaded)

<br>

## ImageField()
- 이미지 업로드에 사용하는 모델 필드

<br>

## 미디어 파일을 제공하기 전 준비
1. settings.py에 MEDIA_ROOT, MEDIA_URL 설정
2. 작성한 MEDIA_ROOT와 MEDIA_URL에 대한 url 지정

<br>

## MEDIA_ROOT
- 미디어 파일들이 위치하는 디렉토리의 절대 경로

<br>

## MEDIA_URL
- MEDIA_ROOT에서 제공되는 미디어 파일에 대한 주소를 생성(STATIC_URL과 동일한 역할)

2023.04.10