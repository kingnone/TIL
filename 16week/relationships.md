# Django - Many to one relationships

<br>

## 관계형 데이터베이스 N:1 관계

<br>

## Foreign Key
- 테이블의 필드 중 다른 테이블의 레코드를 식별할 수 있는 키
- 각 레코드에서 서로 다른 테이블 간의 "관계"를 만드는데 사용

<br>

## Many to one relationships
- N:1 or 1:N
- 한 테이블의 0개 이상의 레코드가 다른 테이블의 레코드 한 개와 관련된 관계

<br>

## Comment 모델 정의
- ForeignKey()클래스의 인스턴스 이름은 참조하는 모델 클래스 이름의 단수형(소문자)으로 작성하는 것을 권장
- ForeignKey 클래스를 작성하는 위치와 관계없이 필드 마지막에 생성됨

<br>

## ForeignKey(to, on_delete)
- to 
  - 참조하는 모델 class 이름
- on_delete
  - 참조하는 모델 class가 삭제 될 때 연결된 하위 객체의 동작을 결정

<br>

## on_delete
- 외래 키가 참조하는 객체(1)가 사라졌을 때, 외래 키를 가진 객체(N)를 어떻게 처리할 지를 정의하는 설정 (데이터 무결성)
- 부모 객체(참조 된 객체)가 삭제 됐을 때 이를 참조하는 객체도 삭제

<br>

## 역참조
- 나를 참조하는 테이블(나를 외래 키로 지정한)을 참조하는 것
- N:1 관계에서는 1이 N을 참조하는 상황

<br>

## related manager
- N:1 혹은 M:N 관계에서 역참조 시에 사용하는 manager
- objects라는 매니저를 통해 queryset api를 사용했던 것처럼 related manager를 통해 queryset api를 사용할 수 있게 됨

<br>

## related manager 가 필요한 이유
- article.comment 형식으로는 댓글 객체를 참조 할 수 없음
- 실제 Article 클래스에는 Comment 와의 어떠한 관계도 작성되어 있지 않기 때문
- 대신 Django가 역참조 할 수 있는 'comment_set' manager를 자동으로 생성해 article.comment_set 형태로 댓글 객체를 참조할 수 있음
- N:1관계에서 생성되는 Related manager의 이름은 참조하는 '모델명_set'이름 규칙으로 만들어짐

2023.04.11