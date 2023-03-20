# Django (Understanding Django and framework)

## Framework
- 웹 애플리케이션을 빠르게 개발할 수 있도록 도와주는 도구
- 개발에 필요한 기본 구조, 규칙, 라이브러리 등을 제공

<br/>

## 프레임 워크를 사용하는 이유
- 기본적인 구조와 규칙을 제공하기 때문에 필수적인 개발에만 집중 할 수 있다
- 여러 라이브러리를 제공해 개발 속도를 빠르게 할 수 있음
- 유지보수와 확장에 용이해 소프트웨어의 품질을 높임

<br/>

## Django
- python 기반의 대표적인 웹 프레임 워크
- 2022 가장 인기있는 백엔드 프레임워크

<br/>

## Django 생성 전 루틴
1. 가상 환경 생성 
  - python -m venv venv
2. 가상 환경 활성화
  - source venv/bin/activate
3. django 설치
  - pip install django==3.2.18
4. 의존성 파일 생성
  - pip freeze > requirements.txt
5. .gitignore 파일 생성 (첫 add전)
6. git 저장소 생성
7. django 프로젝트 생성
  - django-admin startproject firstpjt .
8. django 서버 실행
  - python manage.py runserver
- 5, 6번은 git 관련 설정 시에 실행한다

<br/>

## 가상환경을 사용하는 이유
- 의존성 관리
  - 라이브러리 및 패키지를 각 프로젝트마다 독립적으로 사용가능
- 팀 프로젝트 협업
  - 모든 팀원이 동일한 환경과 의존성 위에서 작업하여 버전간 충돌을 방지

2023.03.20