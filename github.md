# **원격저장소**

## 원격저장소란?
* 소스코드와 버전을 백업하고 다른 사람과 협업을 하기 위한 핵심적인 기능  

<br/>

### **Git**은 버전을 관리한다.  
### **Github** 또한 버전을 관리한다.
<br/>

### git remote      add    origin https://github.com/kdt-live/test.git
###    원격저장소/  추가해/  origin으로/                 유저네임/ 저장소이름  
<br/>

### 기본 원격 저장소 이름 => origin
<br/>

## git 명령어 정리 
### 저장소 처음 생성
* $git init

### 버전을 기록할 때
* $git add .
* $git commit -m '커밋 메시지'

### 상태 확인할 때
* $git status : 1통 2통
* $git log : 커밋 확인

### 원격저장소 활용하기
- 원격 저장소 설정 처음 할 때
- $git remote add origin URL

### push / pull
#### 내가 한거 공유
* $git push

#### 다른 사람 가져오기
* $git pull
<br/>

### $git push origin master
### $git pull origin master
<br/>

### 원격에 있는 프로젝트 시작
* $git clone

### 원격저장소 정보 확인
* $git remote -v

### 원격저장소 추가
* $git remote add <원격저장소(origin)> <URL>

### 원격저장소 삭제
* $git remote rm <원격저장소>

### 원격저장소에 push
* $git push <원격저장소> <브랜치 [master(다른이름으로도 가능)]>

### 원격저장소로부터 pull 
* $git pull <원격저장소> <브랜치 [master(다른이름으로도 가능)]>

*gitghub는 최신 버전의 상태를 보여줄 뿐이다*

*vscode에서 로컬에서 파일을 삭제해도 push 하기전에는 github에는 변화없음*  

<u>변화를 주기 위해서는 git add . -> git commit -m '삭제버전' -> git push origin master</u>
<br/><br/>

### zip 다운로드
* (가장 최신버전의 상태의) 파일만 받음

### clone 다운로드
* git 저장소를 받아오는 것 (모든 버전을 받는다)  
<br/>

### Clone과 Pull의 차이점
* Clone : 원격저장소 복제
* Pull : 원격저장소 커밋 가져오기  
<br/>

## gitignore이란?
* 프로젝트에서 버전 관리를 별도로 하지 않는 파일/디렉토리를 관리하는 것

### .gitignore 사용법
* .ignore를 만들어서 그 안에 내용을 치면 git으로 관리되지 않을 수 있다

#### 예시
* secer.txt
* user/
* *.pptx (*는 .pptx로 끝나는 모든 파일 의미)

*이미 커밋된 것은 gitignore에 쳐도 안된다.*
