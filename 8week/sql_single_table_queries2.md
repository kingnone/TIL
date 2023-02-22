# Single_Table_Queries

## Filtering data
* 데이터를 필터링하고 중복제거, 조건 설정 등  SQL Query를 제어하기

## Filtering data 관련 keyword
* Clause
  * DISTINCT
  * WHERE
  * LIMIT
* Operator
  * BETWEEN
  * IN
  * LIKE
  * Comparison
  * Logical

<br/>

## DISTINCT clause
* 조회 결과에서 중복된 레코드를 제거

## DISTINCT syntax
* SELECT 키웓 바로 뒤에 작성해야 함
* SELECT DISTINCT 키워드 다음에 고유한 값을 선택하려는 하나 이상의 필드를 지정

### DISTINCT ex
* 테이블 employees에서 lastName 필드의 모든 데이터를 중복 없이 오름차순 조회
```sql
SELECT DISTINCT
	lastName
FROM
	employees
ORDER BY
	lastName ASC;
```
<br/>

## WHERE clause
* 조회 시 특정 검색 조건을 지정

## WHERE syntax
* FROM clause 뒤에 위치
* search_condition 은 비교연산자 및 논리연산자(AND, OR, NOT 등)를 사용하는 구문이 사용됨

### WHERE ex 1
* 테이블 employees에서 officeCode 필드 값이 1인 데이터의 lastName, firstName, officeCode 조회
```sql
SELECT
  lastName, firstName, officeCode
FROM
  employees
WHERE
  officeCode = 1;
```

<br/>

### WHERE ex 2
* 테이블 employees에서 jobTitle 필드 값이 'Sales Rep'이 아닌 데이터의 lastName, firstName, jobTitle 조회
```sql
SELECT
  lastName, firstName, jobTitle
FROM
  employees
WHERE
  jobTitle != 'Sales Rep';
```

<br/>

### WHERE ex 3
* 테이블 employees에서 officeCode 필드 값이 3이상이고 jobTitle 필드 값이 'Sales Rep'인 데이터의 lastName, firstName, officeCode, jobTitle 조회
```sql
SELECT
  lastName, firstName, officeCode, jobTitle
FROM
  employees
WHERE
  officeCode >= 3
  AND jobTitle = 'Sales Rep';
```

<br/>

### WHERE ex 4
* 테이블 employees에서 officeCode 필드 값이 5미만이거나 jobTitle 필드 값이 'Sales Rep'이 아닌 데이터의 lastName, firstName, officeCode, jobTitle 조회
```sql
SELECT
  lastName, firstName, officeCode, jobTitle
FROM
  employees
WHERE
  officeCode < 5
  OR jobTitle != 'Sales Rep';
```

<br/>

### WHERE ex 5
* 테이블 employees에서 officeCode 필드 값이 1과 4사이 값인 데이터의 lastName, firstName, officeCode 조회
```sql
SELECT
  lastName, firstName, officeCode
FROM
  employees
WHERE
  officeCode BETWEEN 1 AND 4;
```
```sql
SELECT
  lastName, firstName, officeCode
FROM
  employees
WHERE
  officeCode >= 1
  AND officeCode <= 4;
```

<br/>

### WHERE ex 6
* 테이블 employees에서 officeCode 필드 값이 1과 4사이 값인 데이터의 lastName, firstName, officeCode 를 오름차순 조회
```sql
SELECT
  lastName, firstName, officeCode
FROM
  employees
WHERE
  officeCode BETWEEN 1 AND 4
  ORDER BY officeCode;
```

<br/>

### WHERE ex 7
* 테이블 employees에서 officeCode 필드 값이 1또는 3또는 4 값인 데이터의 lastName, firstName, officeCode 조회
```sql
SELECT
  lastName, firstName, officeCode
FROM
  employees
WHERE
  officeCode IN (1, 3, 4);
```
```sql
SELECT
  lastName, firstName, officeCode
FROM
  employees
WHERE
  officeCode = 1
  OR officeCode = 3
  OR officeCode = 4;
```

<br/>

### WHERE ex 8
* 테이블 employees에서 officeCode 필드 값이 1과 3 그리고 4가 아닌 데이터의 lastName, firstName, officeCode 조회
```sql
SELECT
  lastName, firstName, officeCode
FROM
  employees
WHERE
  officeCode NOT IN (1, 3, 4);
```

<br/>

### WHERE ex 9
* 테이블 employees에서 lastName 필드 값이 son으로 끝나는 데이터의 lastName, firstName를 조회
```sql
SELECT
  lastName, firstName
FROM
  employees
WHERE
  lastName LIKE '%son';
```

<br/>

### WHERE ex 10
* 테이블 employees에서 firstName 필드 값이 4자리면서 y로 끝나는 데이터의 lastName, firstName를 조회
```sql
SELECT
  lastName, firstName
FROM
  employees
WHERE
  firstName LIKE '___y';
```

<br/>

## Comparison Operators
* 비교 연산자 
  * =, >=, <=, !=, IS, LIKE, IN, BETWEEN...AND

<br/>

## Logical Operators
* 논리 연산자
  * AND(&&), OR(||), NOT(!)

<br/>

## IN Operators
* 값이 특정 목록 안에 있는지 확인

<br/>

## LIKE operator
* 값이 특정 패턴에 일치하는지 확인 with Wildcards

<br/>

## Wildcard Characters
* '%' 0개 이상의 문자열과 일치 하는지 확인
* '_' 단일 문자와 일치하는지 확인

<br/>

## LIMIT clause
* 조회하는 레코드 수를 제한

## LIMIT syntax
* LIMIT clause는 하나 또는 두개의 인자를 사용(0 또는 양의 정수)
* row_count는 조회할 최대 레코드 수를 지정
```sql
SELECT
  select_list
FROM
  table_name
LIMIT [offset, ] row_count;
```

### LIMIT ex 1
* 테이블 employees에서 firstName, officeCode 필드 데이터를 officeCode 기준 내림차순으로 7개만 조회
```sql
SELECT
  firstName, officeCode
FROM
  employees
ORDER BY officeCode DESC
LIMIT 7;
```

<br/>

### LIMIT ex 2
* 테이블 employees에서 firstName, officeCode 필드 데이터를 officeCode 기준 내림차순으로 4번째부터 8번째 데이터만 조회
```sql
SELECT
  firstName, officeCode
FROM
  employees
ORDER BY officeCode DESC
LIMIT 3, 5;
```

<br/>

## GROUP BY clause
* 레코드를 그룹화하여 요약본 생성 with 집계 함수

## 집계 함수(Aggregation Functions)
* 값에 대한 계산을 수행하고 단일한 값을 반환하는 함수
  * SUM, AVG, MAX, MIN, COUNT

## GROUP BY syntax
* FROM 및 WHERE 절 뒤에서 배치
* GROUP BY 절 뒤에 그룹화할 필드 목록을 작성

### GROUP BY ex 1
* 테이블 customers에서 country 필드를 그룹화하여 각 그룹에 대한 creditLimit의 평균 값을 내림차순 조회
```sql
SELECT
  country,
  AVG(creditLimit)
FROM
  customers
GROUP BY
  country
ORDER BY 
  AVG(creditLimit) DESC;
```

### GROUP BY ex 2
* 테이블 customers에서 country 필드를 그룹화하여 각 그룹에 대한 creditLimit의 평균 값아 80000을 초과하는 데이터만 조회
```sql
SELECT
  country,
  AVG(creditLimit)
FROM
  customers
GROUP BY
  country
HAVING
  AVG(creditLimit) > 80000;
```

<br/>

### SELECT statement 실행 순서
1. 테이블에서 (FROM)
2. 특정 조건에 맞춰 (WHERE)
3. 그룹화 하고 (GROUP BY)
4. 만약 그룹 중에서 조건이 있다면 맞추고 (HAVING)
5. 조회하여 (SELECT)
6. 정렬하고 (ORDER BY)
7. 특정 위치의 값을 가져온다 (LIMIT)

<br/>

## 정렬에서의 NULL
* mysql에서 NULL은 NULL이 아닌 값 앞에 위치
  * NULL 갑이 존재할 경우 오름차순 정렬 시 결과에 NULL이 먼저 출력

```sql
SELECT
  postalCode
FROM
  customers
ORDER BY
  postalCode;
```

<br/>

2023.02.13