# Django Model

<br/>

## SQLite
- 오픈소스 RDBMS 중 하나이며 django의 기본 DB로 사용됨
- DB가 파일로 존재하며 가볍고 호환성이 좋음

<br/>

## Django Model
- DB의 테이블을 정의하고 데이터를 조작할 수 있는 기능들을 제공
- 테이블 구조를 설계하는 '청사진(blueprint)

<br/>

## Migrations
- model 클래스의 변경사항(필드 생성, 추가 수정 등)을 DB에 최종 반영하는 방법

<br/>

## Migrations 핵심 명령어

<br/>

### python manage.py makemigrations
- model class를 기반으로 설계도(migration) 작성

### python manage.py migrate
- 만들어진 설계도를 DB에 전달하여 반영

<br/>

## CharField()
- 길이의 제한이 있는 문자열을 넣을 때 사용
- 필드의 최대 길이를 결정하는 max_length는 필수 인자

<br/>

## TextField()
- 글자의 수가 많을 때 사용

<br/>

## DateTimeField()
- 날짜와 시간을 넣을 때 사용

<br/>

## DateTimeField의 선택인자

<br/>

### auto_now
- 데이터가 저장될 때마다 자동으로 현재 날짜시간을 저장

<br/>

### auto_now_add
- 데이터가 처음 생성될 때만 자동으로 현재 날짜시간을 저장

<br/>

## Automatic admin interface
- django는 추가 설치 및 설정 없이 자동으로 관리자 인터페이스를 제공

<br/>

## admin 계정 생성
- python manage.py createsuperuser
## DB에 생성된 admin 계정 확인
## admin에 모델 클래스 등록
## 로그인 후 등록된 모델 클래스 확인
## 데이터 CRUD 테스트

<br/>

## 데이터베이스 초기화
1. migration 파일 삭제
2. db.sqlite3 파일 삭제
- *migration 폴더를 지우지 않도록 주의*

<br/>

## Migrations 기타 명령어
- python manage.py showmigrations
  - migrations 파일들이 migrate 됐는지 안됐는지 여부를 확인하는 용도
- python manage.py sqlmigrate articles 0001
  - 해당 migrations 파일이 SQL 문으로 어떻게 해석 되어 DB에 전달되는지 확인하는 용도

<br/>

## 첫 migrate 시 출력 내용이 많은 이유는?
- 기본적으로 Django 프로젝트가 동작하기 위해 작성 되어있는 기본 내장 app들에 대한 migration 파일들이 함께 migrate 되기 때문

2023.03.24