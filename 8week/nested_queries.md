# **Nested Queries**

## Subquery
* 단일 쿼리문에 여러 테이블의 데이터를 결합하는 방법

## subquery 특징
* 조건에 따라 하나 이상의 테이블에서 데이터를 검색하는 데 사용
* SELECT, FROM, WWHERE, HAVING  절 등에서 다양한 맥락에서 사용

## subquery syntax
* 가장 나이가 적은 사람 찾기
```sql
SELECT MIN(age)
FROM table1;
```
* 가장 나이가 적은 사람 삭제
```sql
DELETE FROM table1
WHERE age = (
    SELECT MIN(age) FROM table1
);
```

### subquery ex 1
* 가장 많은 돈을 소비한 고객 번호 조회(payments 테이블 활용)
```sql
SELECT customerNumber, amount
FROM payments
WHERE amount = (
	SELECT max(amount)
    FROM payments
);
```

<br/>

### subquery ex 2
* 미국에 있는 사무실에서 근무하는 직원의 이름과 성 조회
(직원 정보는 employees, 사무실 정보는 offices 테이블에 존재)
```sql
SELECT lastName, firstName
FROM employees
WHERE officeCode IN (
	SELECT officeCode
	FROM offices
	WHERE country = 'USA'
);
```

<br/>

### subquery ex 3
* 주문한 적이 없는 고객 목록 조회
(고객 정보는 customers, 주문 정보는 orders 테이블에 존재)
```sql
SELECT lastName, firstName
FROM employees
WHERE officeCode IN (
	SELECT officeCode
	FROM offices
	WHERE country = 'USA'
);
```

<br/>

### subquery ex 4 (1번 예시 심화 버전)
* 소비를 한 고객들 중 지불한 금액이 가장 높은 고객의 customerNumber, amount, contactFirstName을 조회
(고객 테이블은 customers, 지불 테이블은 payments를 활용)
```sql
SELECT customerNumber, amount, contactFirstName
FROM (
	SELECT *
    FROM payments
    INNER JOIN customers USING (customerNumber)
) AS mysub
WHERE amount = (
	SELECT max(amount)
    FROM payments
);
```

<br/>

## EXISTS operator
* 쿼리 문에서 반환된 레코드의 존재 여부를 확인

## EXISTS syntax
* subquery가 하나 이상의 행을 반환하면 EXISTS 연산자는 true를 반환하고 그렇지 않으면 false를 반환
* 주로 WHERE 절에서 subquery의 반환 값 존재 여부를 확인하는데 사용
```sql
SELECT
  select_list
FROM
  table
WHERE
  [NOT] EXISTS (subquery);
```

### EXISTS ex 1
* 적어도 한번 이상 주문을 한 고객들의 번호와 이름 조회
(고객 테이블은 customers, 주문 테이블은 orders이며 두 테이블의 customerNumber 필드를 기준으로 비교)
```sql
SELECT customerNumber, customerName
FROM customers
WHERE EXISTS (
	SELECT *
    FROM orders
    WHERE customers.customerNumber = orders.customerNumber
);
```

<br/>

## EXISTS ex 2
* Paris에 있는 사무실에서 일하는 모든 직원의 번호, 이름, 성을 조회
(직원 테이블은 employees, 사무실 테이블은 offices이며 두테이블의 officeCode 필드를 기준으로 비교)
```sql
SELECT employeeNumber, firstName, lastName
FROM employees
WHERE EXISTS (
	SELECT *
    FROM offices
    WHERE
		city = 'Paris' AND
        offices.officeCode = employees.officeCode
);
```

<br/>

## CASE statement
* SQL 문에서 조건문을 구성

## CASE syntax 
* case_value가 when_value와 동일한 것을 찾을때까지 순차적으로 비교
* when_value와 동일한 case_value를 찾으면 해당 THEN 절의 코드를 실행
* 동일한 값을 찾지 못하면 ELSE절의 코드를 실행
  * ELSE 절이 없을 때 동일한 값을 찾지 못하면 오류 발생
```sql
CASE case_value
  WHEN when_value1 THEN statements
  WHEN when_value2 THEN statements
  ...
  [ELSE else-statements]
END CASE;
```

### CASE ex 1
* 고객들의 creditLimit에 따라 VIP, Platinum, Bronze 등급을 매겨 조회
(VIP는 100000 초과, Platinum은 70000 초과 그 외는 Bronze로 지정)
```sql

```

<br/>

### CASE ex 2
* orders 테이블의 status에 따라 상세 정보를 매겨 조회
('In Progress'는 '주문중', 'Shipped'는 '발주완료', 'Cancelled'는 '주문취소' 그 외는 '기타사유'로 지정)
```sql
SELECT orderNumber, status,
	CASE
		WHEN status = 'In Process' THEN '주문중'
        WHEN status = 'Shipped' THEN '발주완료'
        WHEN status = 'Cancelled' THEN '주문취소'
	END AS details
FROM orders;
```

2023.02.16