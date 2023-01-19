# **GIT 정리**
---
## git이란?

* git은 분산버전관리시스템으로 코드의 버전을 관리

* 2005년 리눅스 커널을 위한 도구로 리누스 토르발스(화가 많은 사람ㅎ)가 개발

* 컴퓨터 파일의 변경사항을 추적하고 사용자들 간에 해당 파일들의 작업을 조율

## git 기본 명령어

* git init란 특정 폴더를 git 저장소를 만들어 git으로 관리

* git add란 staging area에 추가하기 위해 사용

* git commit -m '<커밋메시지>'는 staged 상태의 파일들을 커밋을 통해 버전으로 기록

* git log란 현재 저장소에 기록된 커밋을 조회

* git status란 git 저장소에 있는 파일의 상태를 확인하기 위해 활용
  * Status로 확인 가능한 파일의 상태 
  
  * tracked : 이전부터 버전으로 관리되고 있는 파일
  * Unmodified : git status에 나타나지 않음
  * Modified : Change no staged for commit
  * Staged : Changes to be commit
  
  * Untracked : 버전으로 관리된 적 없는 파일(파일을 새로 만든 경우)

## 버전 관리하는 방법

1. 작업을 하고
2. 변경된 파일을 모아 (add)
3. 버전으로 남긴다 (commit)


## 과정

* 1통 = add 하기 전에 상태 
* 2통 = add 한 후 상태 git에 저장소에 등록된 상태
* 3통 = 커밋들이 기록되는 곳

2022.12.27