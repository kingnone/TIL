# **Multi Table Queries**

# Introduction to join

## 관계형 데이터베이스
* 데이터 간에 관계가 있는 데이터 항목들의 모ㅁ

## 관계
* 여러 테이블 간의 (논리적) 연결

<br/>

# Joining Table

## JOIN clause
* 둘 이상의 테이블에서 데이터를 검색하는 방법

## JOIN 종류
* INNER JOIN
* OUTER JOIN
  * LEFT JOIN
  * RIGHT JOIN
* CROSS JOIN

<br/>

## INNER JOIN clause
* 두 테이블에서 값이 일치하는 레코드에 대해서만 결과를 반환

## INNER JOIN syntax
* FROM 절 이후 메인 테이블 지정 (table1)
* INNER JOIN 절 이후 메인 테이블과 조인할 테이블을 지정 (table2)
* ON 키워드 이후 조인 조건 작성
  * 조인 조건은 table1과 table2 간의 레코드를 일치시키는 규칙을 지정
```sql
SELECT
  select_list
FROM
  table1
INNER JOIN table2
  ON table1.fk = table2.pk;
```

### INNER JOIN ex 1
* productLine 값이 같은 레코드의 productCode, productName, textDescription 필드를 조회
```sql
SELECT
	productCode, productName, textDescription
FROM
	products
INNER JOIN productlines
	ON products.productLine = productlines.productLine;
```

<br/>

### INNER JOIN ex 2
* orderNumber 값이 같은 레코드의 orders 테이블 orderNumber, status 필드를 조회
```sql
SELECT
	orders.orderNumber, status, priceEach
FROM
	orders
INNER JOIN orderdetails
	ON orders.orderNumber = orderdetails.orderNumber;
```

<br/>

### INNER JOIN ex 3
* 각 주문번호 별 주문상태와 총 판매액을 요약 (주문 번호는 orderNumber 필드, 총 판매액은 quantityOrdered와 priceEach 필드의 곱셈 결과)
```sql
SELECT 
	orders.orderNumber,
    status,
    SUM(priceEach * quantityOrdered)
FROM
	orders
INNER JOIN orderdetails
	ON orders.orderNumber = orderdetails.orderNumber
GROUP BY
	orderNumber;
```

<br/>

## LEFT JOIN clause
* 오른쪽 테이블의 일치하는 레코드와 함께 왼쪽 테이블의 모든 레코드 반환

## LEFT JOIN syntax
* FROM 절 이후에 왼쪽 테이블 지정 (table1)
* LEFT JOIN 절 이후 오른쪽 테이블 지정 (table2)
* ON 키워드 이후 조인 조건을 작성
  * 왼쪽 테이블의 각 레코드를 오른쪽 테이블의 모든 레코드와 일치시킴
```sql
SELECT
  select_list
FROM
  table1
LEFT [OUTER] JOIN table2
  ON table1.fk = table2.pk;
```

## LEFT JOIN 특징
* 왼쪽은 무조건 표시하고, 매치되는 레코드가 없으면 NULL을 표시
* 왼쪽 테이블 한 개의 레코드에 여러 개의 오른쪽 테이블 레코드가 일치할 경우, 해당 왼쪽 레코드를 여러 번 표시

<br/>

### LEFT JOIN ex 1
* customers를 기준으로 customerNumber 필드가 일치하는 레코드와 함께 customers 테이블 contactFirstName 와 orders 테이블의 orderNumber, status 필드 조회 (왼쪽 테이블은 customers, 오른쪽 테이블은 orders, 일치하지 않는 경우 NULL)
```sql
SELECT
  contactFirstName,
  orderNumber,
  status
FROM
  customers
LEFT JOIN orders
  ON orders.customerNumber = customers.customerNumber;
```

<br/>

### LEFT JOIN ex 2
* 주문내역이 없는 고객의 이름과 주문번호 및 배송상태 조회
(고객의 이름은 contactFirstName 필드, 주문번호는 orderNumber, 배송 상태는 status 필드)
```sql
SELECT
  contactFirstName,
  orderNumber,
  status
FROM
  customers
LEFT JOIN orders
  ON orders.customerNumber = customers.customerNumber
WHERE
  orders.orderNUmber IS NULL;
```

<br/>

## RIGHT JOIN clause
* 왼쪽 테이블의 일치하는 레코드와 함께 오른쪽 테이블의 모든 레코드 반환

## RIGHT JOIN syntax
* FROM 절 이후 왼쪽 테이블 지정 (table1)
* RIGHT JOIN 절 이후 오른쪽 테이블 지정 (table2)
* ON 키워드 이후 조인 조건을 작성
  * 오른쪽 테이블의 각 레코드를 왼쪽 테이블의 모든 레코드와 일치시킴
```sql
SELECT
  select_list
FROM
  table1
RIGHT [OUTER] JOIN table2
  ON table1.fk = table2.pk;
```

## RIGHT JOIN 특징
* 오른쪽은 무조건 표시하고, 매치되는 레코드가 없으면 NULL을 표시
* 오른쪽 테이블 한 개의 레코드에 여러 개의 왼쪽 테이블 레코드가 일치하는 경우, 해당 오른쪽 레코드를 여러 번 표시

### RIGHT JOIN ex 1
* employees를 기준으로 employeeNumber 필드와 salesRepEmployeeNumber 필드가 일치하는 레코드와 함께 employeeNumber, firstName, customerNumber, contactFirstName 필드 조회
(왼쪽 테이블 customers, 오른쪽 테이블은 employees, 일치하지 않는 경우 NULL)
```sql
SELECT
  employeeNumber,
  firstName,
  customerNumber,
  contactFirstName
FROM
  customers
RIGHT JOIN employees
  ON salesRepEmployeeNumber = employeeNumber;
```

<br/>

### RIGHT JOIN ex 2
* 고객에게 판매한 내역이 없는 직원 목록 조회
(직원 번호와 이름은 employeeNumber, contactFirstName 필드이며 고객 번호와 이름은 customerNumber, contactFirstName 필드)
```sql
SELECT
  employeeNumber,
  firstName,
  customerNumber,
  contactFirstName
FROM
  customers
RIGHT JOIN employees
  ON salesRepEmployeeNumber = employeeNumber
WHERE
  salesRepEmployeeNumber IS NULL;
```

<br/>

2023.02.15