# **Modifying Data**

# Insert data into table

## INSERT statement
* 테이블 레코드 삽입

## INSERT syntax
* INSERT INTO 절 다음에 테이블 이름과 괄호 안에 필드 목록을 작성
* VALUES 키워드 다음 괄호 안에 해당 필드에 삽입할 값 목록을 작성
```sql
INSERT INTO table_name (c1, c2, ...)
VALUES (v1, v2, ...);
```

### INSERT ex 1
* articles 테이블에 각 필드에 적합한 데이터 입력
```sql
INSERT INTO
  artcles (title, content, createdAt)
VALUES
  ('hello', 'world', '2000-01-01');
```

<br/>

### INSERT ex 2
* articles 테이블에 각 필드에 적합한 데이터 3개 입력
```sql
INSERT INTO
  articles (title, content, createdAt)
VALUES
  ('title1', 'content1', '1900-01-01'),
  ('title2', 'content2', '1800-01-01'),
  ('title3', 'content3', '1700-01-01');
```

<br/>

### INSERT ex 3
* articles 테이블에 각 필드에 적합한 데이터 입력 (단, createAt 필드에는 현재 작성하는 날짜가 자동으로 입력 나머지 필드 자율)
```sql
INSERT INTO
  articles (title, content, createdAt)
VALUES
  ('mytitle', 'mycontent', CURDATE());
```

<br/>

# Update data in table

## UPDATE statement
* 테이블 레코드 수정

## UPDATE syntax
* SET 절 다음에 수정 할 필드와 새 값을 지정
* WHERE 절에서 수정 할 레코드를 지정하는 조건 작성
  * WHERE 절을 작성하지 않으면 모든 레코드를 수정

### UPDATE ex 1
* articles 테이블 1번 레코드의 title 필드 값을 'newTitle'로 변경
```sql
UPDATE
  articles
SET
  title = 'newTitle'
WHERE
  id = 1;
```

<br/>

### UPDATE ex 2
* articles 테이블 2번 레코드의 title, content 필드 값을 자유롭게 변경
```sql
UPDATE
  articles
SET
  title = 'newTitle',
  content = 'newContent'
WHERE
  id = 2;
```

<br/>

### UPDATE ex 3
* articles 테이블 모든 레코드의 content 필드 값 중 문자열 'content'를 'TEST'로 변경
```sql
UPDATE
  articles
SET
  content = REPLACE(content, 'content', 'TEST');
```

<br/>

# Delete data from table

## DELETE statement
* 테이블 레코드 삭제

## DELETE syntax
* DELETE FROM 절 다음에 테이블 이름 작성
* WHERE 절에서 삭제할 레코드를 지정하는 조건 작성
  * WHERE절을 작성하지 않으면 모든 레코드 삭제
```sql
DELETE FROM table_name
[WHERE
  condition];
```

### DELETE ex 1
* articles 테이블의 1번 레코드 삭제
```sql
DELETE FROM
  articles
WHERE
  id = 1;
```

<br/>

### DELETE ex 2
* articles 테이블에서 가장 최근에 작성된 레코드 삭제
```sql
DELETE FROM
  articles
ORDER BY
  createdAt DESC
LIMIT 2;
```

<br/>

2023.02.14