# **Advanced**

# Transactions

## Transaction
* 여러 쿼리문을 묶어서 하나의 작업처럼 처리하는 방법

## Transaction 예시
* 계좌이체 (인출 & 입금)
  * 송금 중에 알 수 없는 문제로 인출에는 성공했는데 입금에 실패하다면?
  * 인출과 입금 모두 성공적으로 끝나야 거래가 최종 승인되고, 중간에 문제가 발생한다면 거래를 처음부터 없었던 거래로 만들어야함
  * 결국 함께 성공하던지 실패해야 함

## Transaction syntax
* START TRANSACTION
  * 트랜젝션 구문의 시작을 알림
* COMMIT
  * 모든 작업이 정상적으로 완료되면 한꺼번에 DB 저장
* ROLLBACK
  * 부분적으로 작업이 실패하면 트랜잭션에서 진행한 모든 연산을 취소하고 트랜잭션 실행전을 되돌림
```sql
START TRANSACTION;
state_ments;
...
[ROLLBACK|COMMIT];
```

### Transaction ex 1
* 트랜잭션을 사용해 users 테이블에 데이터를 삽입하고 ROLLBACK을 했을 때와 COMMIT을 했을 때 users 테이블의 데이터 상태 비교
```sql
START TRANSACTION;

INSERT INTO users (name)
VALUES ('james'), ('mary');

SELECT * FROM users;

ROLLBACK;

SELECT * FROM users;
```

```sql
START TRANSACTION;

INSERT INTO users (name)
VALUES ('james'), ('mary');

SELECT * FROM users;

COMMIT;

SELECT * FROM users;
```

## Transaction 정리
* 쪼개질 수 업는 업무처리의 단위
* 전체가 수행되거나 또는 전혀 수행되지 않아야 함 (All or Nothing)

# Triggers

## Triggers
* 특정 이벤트에 대한 응답으로 자동으로 실행되는 것
* ~를 추가한 후에 ~하겠다
* ~를 수정하기 전에 ~하겠다
* ~ 를 삭제한 후에 ~하겠다
* ~하겠다 부분이 Trigger

## Triggers syntax
* CREATE TRIGGER 키워드 다음에 생성하려는 트리거의 이름을 지정
* 각 레코드의 어느 시점에 트리거가 실행될지 지정 (삽입, 수정, 삭제)
* ON 키워드 뒤에 트리거가 속한 테이블의 이름을 지정
* 트리거가 활성화 될 때 실행할 코드를 trigger_body에 지정
  * 여러 명령문을 실행하려면 BEGIN END 키워드로 묶어서 사용
```sql
CREATE TRIGGER trigger_name
{BEFORE | AFTER} {INSERT | UPDATE | DELETE}
ON table_name FOR EACH ROW
trigger_body;
```

### Triggers ex 1
* 트리거를 사용해 기존 게시글이 수정되면, 게시글의 수정일자 필드 값을 최신 일자로 업데이트 하기
```sql
DELIMITER //
CREATE TRIGGER beforeArticleUpdate
	BEFORE UPDATE
    ON articles FOR EACH ROW
BEGIN
	SET NEW.updateAt = CURRENT_TIME();
END//
DELIMITER ;
```

<br/>

### Triggers ex 2
* 트리거를 사용해 기존 게시글이 작성되면, 별도의 테이블에 해당 게시글이 작성되었다는 것을 기록하기
```sql
DELIMITER //
CREATE TRIGGER recordLogs
	AFTER INSERT
    ON articles FOR EACH ROW
BEGIN 
	INSERT INTO articleLogs (description, createAt)
    VALUES ('글이 작성 되었습니다.', CURRENT_TIME());
END//
DELIMITER ;
```

<br/>

### Triggers ex 심화
* 트리거를 사용해 기존 게시글이 작성되면, 별도의 테이블에 몇 번 게시글이 작성되었다는 것을 기록하기
```sql
DELIMITER //
CREATE TRIGGER recordLogs
	AFTER INSERT
    ON articles FOR EACH ROW
BEGIN 
	INSERT INTO articleLogs (description, createAt)
    VALUES (CONCAT(NEW.id, '번 글이 작성 되었습니다.'), CURRENT_TIME());
END//
DELIMITER ;
```

<br/>

### Triggers ex 3
* 트리거를 사용해 기존 게시글이 삭제되면, 삭제돈 게시글의 구조 그대로 별도의 테이블에 기록하기
```sql
DELIMITER //
CREATE TRIGGER backUpLogs
	AFTER DELETE
	ON articles FOR EACH ROW
BEGIN
	INSERT INTO backupArticles (title, createAt, updateAt)
    VALUES (OLD.title, OLD.createAt, OLD.updateAt);
END//
DELIMITER ;
```

<br/>

## Triggers 관련 추가 명령문
```sql
-- 트리거 목록 확인
SHOW TRIGGERS;

-- 트리거 삭제
DROP TRIGGER trigger_nane;
```

<br/>

## Triggers 생성 시 에러 해결
* 트랜잭션 생성 후 정상 적으로 종료되지 않아 발생하는 에러 발생 시 해결 법
* Error Code:2013.Lost connection to MySQL server during query
* Error Code:2015.Lock wait timeout exceeded; try restarting transaction
```sql
-- 실행중인 프로세스 목록 확인
SELECT * FROM information_schema.INNODB_TRX;

-- 특정 프로세스의 trx_mysql_thread_id 삭제
KILL [trx_mysql_thread_id1];
```

<br/>

2023.02.20