# ORM

<br/>

## 데이터 수정
- 수정할 인스턴스 조회
  - article = Article.objects.get(pk=1)
- 인스턴스 변수를 변경
  - article.title = 'byebye'
- 저장
  - article.save()
- 정상적으로 변경된 것을 확인
  - article.title

<br/>

## 데이터 삭제
- 삭제할 인스턴스 조회
  - article = Article.objects.get(pk=1)
- delete 메서드 호출 (삭제 된 객체가 반환)
  - article.delete()

<br/>

2023.03.29