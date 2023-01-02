# Python_basics

### 파이썬 2주 + 알고리즘 3주

### '코드' 결국에는 도구 중에 하나일 뿐입니다.

## 컴퓨터 (computer)
* Caculation (조작)
* Remember   (저장)

## 프로그래밍 (programming)
* 명령어의 모음(집합)
* 언어 = 자신의 생각을 나타내고 전달하기 위해 사용하는 체계
* 문법적으로 맞는 말의 조합
* 컴퓨터에게 명령하기 위한 약속

## 선언적 지식 (declarative Knowledge)
* "사실에 대한 내용"
## 명령적 지식 (imperative konwledge)
* "How-to"

## 파이썬(Python)이란?
*다른 프로그래밍 언어보다 문법이 간단하면서도 엄격하지 않음

## 인터프리터 언어
* 소스코드를 기계어로 변환하는 컴파일 과정 없이 바로 실행 가능

## 객체 지향 프로그래밍
* 파이썬은 객체지향 언어이며 모든것이 객체로 구현되어 있음

## 객체(Object)

## 변수
* 변수는 할당 연산자(=)를 통해 값을 할당

### type()
* 변수에 할당된 값의 타입

### id()
* 변수에 할당된 값(객체)의 고유한 아이덴티티 값이며, 메모리 주소

#### x=10 y=20일 때, 각각 값을 바꿔서 저장하는 코드
* tmp = x
* x = y
* y= tmp
* print(x, y)

* y, x = x, y
* print(x, y)

## 식별자
* 파이썬 객체(변수, 함수, 모듈, 클래스 등)를 식별하는데 사용하는 이름
### 규칙
* 식별자의 이름은 영문 알파벳, 언더스코어(_), 숫자로 구성
* 첫 글자에 숫자가 올 수 없음
* 길이제한이 없고, 대소문자를 구별

## 수치형

### 정수
* 모든 정수의 타입은 int 
* 매우 큰 수를 나타낼 때 오버플로우가 발생하지 않음

### 실수
* 정수가 아닌 모든 실수는 float 타입
* 부동소수점

### 불린형
* True / False 값을 가진 타입은 bool
* 비교/논리 연산을 수행함에 있어서 활용됨

## 연산자
### 산술 연산자
* + 덧셈
* - 뺄셈
* * 곱셈
* % 나머지
* / 나눗셈
* // 몫
* ** 거듭제곱

### 복합 연산자
* a += b	a = a + b
* a -= b 	a= a - b
* a *= b	a = a * b
* a /= b	a = a / b
* a //= b	a = a // b
* a %= b	a = a % b
* a **= b	a = a ** b

### 비교 연산자 
* <  미만
* <= 이하
* ">" 초과
* ">=" 이상
* == 같음
* != 같지않음

### 논리 연산자
* A and B  A와 B 모두 True시 , True
* A or B   A와 B 모두 False시, False
* Not 	 True를 False로, False를 True로

#### and : 모두 참인 경우 참, 그렇지 않으면 거짓
* True and True	True
* True and Flase  False
* False and True	False
* Flase and False	False

#### or : 둘 중 하나만 참이라도 참, 그렇지 않으면 거짓
* True or True 	True
* True or False	True
* False or True	True
* False or False	True

#### not : 참 거짓의 반대의 결과
* not True 	False
* not False	True

## 컨테이너 정의
### 컨테이너란? 
* 여러 개의 값을 담을 수 있는 것으로 서로 다른 자료형을 저장할 수 있음

### 컨테이너의 분류
* 순서가 있는 데이터 vs 순서가 없는 데이터
* 순서가 있다 != 정렬되어 있다.

## 문자열(string type)
* 모든 문자는 str 타입
* 문자열은 작은 따옴표(') 나 큰 따옴표(")를 활용해 표기

### 중첩따옴표
* 따옴표 안에 따옴표를 표현할 경우
* print("문자열 안에 '작은 따옴표'를 사용하려면 큰 따옴표로 묶는다")
* print('문자열 안에 "작은 따옴표"를 사용하려면 큰 따옴표로 묶는다')

### 삼중따옴표
* 작은 따옴표나 큰 따옴표를 삼중으로 사용 
* 따옴표 안에 따옴표를 넣을 때, 여러줄을 나눠 입력할 때 편리 
* print('''문자열 안에 '작은 따옴표'나 <br/>
"큰 따옴표"를 사용할 수 있고 <br/>
여러 줄을 사용할 때도 편리하다.'''

## 리스트(Lits)정의
* 변경 가능한 값들의 나열된 자료형
* 순서를 가지며, 서로 다른 타입의 요소를 가질 수 있음
* 변경 가능하며, 반복 가능함
* 항상 대괄호 형태로 정의하며, 요소는 콤마로 구분

## none
* 파이썬 자료형 중 하나
* 파이썬에서는 값이 없음을 표현하기 위해 None 타입이 존재함
* 일반적으로 반환 값이 없는 함수에서 사용하기도 함

## 주석
* 코드에 대한 설명
* 주석으로 처리될 내용 앞에 #을 입력

## 단축키
* 파일 처리하기 ctrl + s
* 파일 만들기 ctrl + n 
* 주석처리하기 ctrl + / 

## 언어 학습 4가지 방법 
- 말하기 
- 듣기
- 쓰기
- 읽기 

2023.01.02