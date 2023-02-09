# Single_Table_Queries

## Querying data
### SELECT statement
* 테이블에서 데이터를 조회
* SELECT 키워드 다음에 데이터를 선택하려는 필드를 하나 이상 지정
* FROM 키워드 다음에 데이터를 선택하려는 데이블의 이름을 지정

<br/>

### SELECT * FROM 테이블명;
* 테이블에 해당하는 모든 필드의 데이터를 조회
### SELECT FirstName as '이름' FROM 테이블명;
* FirstName으로 출력되는 것이 아닌 이름으로 출력 될 수 있도록 출력명 변경
* AS keyword는 필드에 새로운 별칭을 지정
### SELECT productCode, quantityOrdered * priceEach as '주문 총액' FROM 테이블명;d
* quantityOrdered 와 priceEach 를 곱해서 주문 총액으로 별칭을 지어서 출력해줌
### 주석 처리 방법
* -- 이 주석 처리

<br/>

## Sorting data
### ORDER BY clause
* 조회 결과의 레코드를 정렬
* FROM clause 뒤에 위치
* 하나 이상의 컬럼을 기준으로 결과를 오름차순, 내림차순으로 정렬할 수 있음
* ASC : 오름차순 (기본값)
* DESC : 내림차순

<br/>

### SELECT FirstName FROM employees ORDER BY FirstName;
* employees에서 firstname 필드의 모든 데이터를 오름차순으로 조회
### SELECT FirstName FROM employees ORDER BY FirstName DESC;
* employees에서 firstname 필드의 모든 데이터를 내림차순으로 조회
### SELECT LastName, FirstName FROM employees ORDER BY LastName DESC, FirstName;
* lastname 필드를 기준으로 내림차순으로 정렬한 다음 firstname 필드 기준으로 오름차순 정렬하여 조회
### SELECT productCode, quantityOrdered * priceEach AS totalSales FROM orderdetails ORDER BY totalSales DESC;
* orderdetails에서 totalSales 필드를 기준으로 내림차순으로 정렬한 다음 productCode, totalSales 필드의 모든 데이터를 조회
(단, totalSales 필드는 quantityOrdered와 priceEach 필드를 곱한 결과 값)

<br/>

## SELECT statement 실행 순서
* FROM -> SELECT -> ORDER BY
1. 테이블에서 (FROM)
2. 조회하여 (SELECT)
3. 정렬 (ORDER BY)

2023.02.09