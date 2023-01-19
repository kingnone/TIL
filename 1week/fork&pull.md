# **Branch**

## Branch란?
* 협업을 위해 독립적인 작업 흐름 만들기


## 브렌치 주요 명령어
### git branch 생성
* $git branch 원하는 이름

### branch 변환
* $git checkout 원하는 이름

### branch 합치기
* $git merge 원하는 이름

### branch 끝내기
* $git branch -d 원하는 이름

### branch 생성 및 이동
* $git checkout -b 원하는 이름 
* 원하는 이름의 branch가 없을때 checkout만 쓰면 없다고 오류 메세지가 뜨는데 -b옵션을 통해 새롭게 생성하면서 바꿀 수 있다

### add를 한 파일은 빼고 싶을 때
* $git restore --staged 이름

### 코드 되돌리기
* $git restore 파일 이름

### 커밋 메세지 수정 
* *그렇지만 메세지를 수정하면 해시값이 달라져서 히스토리가 사라진다*
* $git commit --amend


## Git flow
* git을 활용하여 협업하는 흐름으로 branch를 사용하는 것과 같다 

## git flow 기본 원칙
* master branch 배포 가능 상태  
* feature 의도를 알 수 있게 작성  
* commit message 명확하게 작성  
* pull request 협업 진행  

## 혼자 작업할때 
 1.브렌치 만들고

 2.작업 
 
 3.커밋 
 
 4.로컬에서 master 이동 병합 

## github flow (협업할때)
 1.브렌치 만들고 
 
 2.작업
 
 3.커밋
 
 4.github으로 브렌치 push
 
 5.pull request
 
 (리뷰 과정이 들어갈 수 있다) 
 
 6.merge

2022.12.29