# Basic syntax of JavaScript

## 식별자 (변수명) 작성 규칙
* 반드시 문자, 달러($) 또는 밑줄(...)로 시작
* 대소문자를 구분하며, 클래스명 외에는 모두 소문자로 시작
* 에약어 사용 불가
  * for, if, function 등
* 카멜 케이스 (camelCase)
  * 변수, 객체, 함수에 사용
* 파스칼 케이스 (PascalCase)
  * 클래스 생성자에 사용
* 대문자 스네이크 케이스 (SNAKE_CASE)
  * 상수 (constants)에 사용
  * 상수 : 개발자의 의도와 상관없이 변경될 가능성이 없는 값
  
<br/>

## 변수 선언 키워드
1. let
  * 블록 스코프를 갖는 지역 변수를 선언
  * 재할당 가능 & 재선언 불가능
2. const
  * 블록 스코프를 갖는 지역 변수를 선언
  * 재할당 불가능 & 재선언 불가능
3. var

<br/>

## 블록 스코프(block scope)
* if, for, 함수 등의 중괄호({}) 내부를 가리킴
* 블록 스코프를 가지는 변수는 블록 바깥에서 접근 불가능

<br/>

## 변수 선언 키워드 정리
* 기본적으로 const 사용을 권장
* 재할당해야 하는 경우만 let을 사용
* 다만, 실습에서는 편의를 위해 재할당이 가능한 let을 기본적으로 사용

<br/>

## 원시 자료형
* Number, String, Boolean, undefined, null
* 변수에 값이 직접 저장되는 자료형 (불변, 값이 복사)

## 참조 자료형
* objects (object, Array, Function)
* 객체의 주소가 저장되는 자료형 (가변, 주소가 복사)

<br/>

## 용어 정리
* Number
  * 정수 또는 실수형 숫자를 표현하는 자료형
* String
  * 텍스트 데이터를 표현하는 자료형
* null 
  * 변수의 값이 없음을 의도적으로 표현할 때 사용
* undefined 
  * 변수 선언 이후 직접 값을 할당하지 않으면 자동으로 할당됨

<br/>

## Null 과 undefined
* 동일한 역할을 하는 이 두개의 키워드가 존재하는 이유는 단순한 javascript의 설계 실수
* null이 원시 자료형임에도 불구하고 object로 출력되는 이유는 javascript설계 당시의 버그를 해결하지 못한 것

<br/>

## 할당 연산자
* 오른쪽에 있는 피연산자의 평가 결과를 왼쪽 피연산자에 할당하는 연산자
* 다양한 연산에 대한 단축 연산자 지원
* Increment(++)
  * 피연산자의 값을 1 증가시키는 연산자
* Decrement(--)
  * 피연산자의 값을 1 감소시키는 연산자
* += 또는 -=와 같이 더 분명한 표현으로 적을 것을 권장

<br/>

## 비교 연산자
* 피연산자들(숫자, 문자, Boolean등)을 비교하고 결과값을 boolean으로 반환하는 연산자

<br/>

## 동등 연산자 (==)
* 두 피연산자가 같은 값으로 평가되는지 비교 후 boolean 값을 반환
* 비교할 때 암묵적 타입 변환 통해 타입을 일치시킨 후 같은 값인지 비교
* 두 피연산자가 모두 객체일 경우 메모리 같은 객체를 바라보는지 판별
* 예상치 못한 결과가 발생할 수 있으므로 특별한 경우를 제외하고 사용하지 않음

<br/>

## 일치 연산자 (===)
* 두 피연산자의 값과 타입이 모두 같은 경우 true를 반환
* 같은 객체를 가리키거나, 같은 타입이면서 같은 값인지를 비교
* 엄격한 비교가 이뤄지며 암묵적 타입 변환이 발생하지 않음

<br/>

## 논리 연산자
* and 연산은 '&&'
* or 연산은 '||'
* not 연산은 '!'

<br/>

## 조건문
* if 
  * 조건 표현식의 결과값을 boolean 타입으로 변환 후 참/거짓을 판단

<br/>

## 반복문 
* while
  * 조건문이 참이기만 하면 문장을 계속해서 수행
* for
  * 특정한 조건이 거짓으로 판별될 때까지 반복
* for..in
  * 객체의 속성을 순회할 때 사용
  * 객체 속성에 대해 반복
* for..of
  * 반복 가능한 객체를 순회할 때 사용
  * 객체 요소에 대한 반복

<br/>

## 세미콜론 (semicolon)
* 자바스크립트는 세미콜론을 선택적으로 사용 가능
* 세미콜론이 없으면 ASI에 의해 자동으로 세미콜론이 삽입됨

<br/>

## Var
* 재할당 가능 & 재선언 가능
* ES6 이전에 변수를 선언할 때 사용되던 키워드
* 호이스팅 되는 특성으로 인해 예기치 못한 문제 발생 가능
* 함수 스코프를 가짐
* 변수 선언시 var const, let 키워드 중 하나는 사용하지 않으면 자동으로 var로 선언됨

<br/>

## 함수 스코프 (function scope)
* 함수의 중괄호 내부를 가리킴
* 함수 스코프를 가지는 변수는 함수 바깥에서 접근 불가능

<br/>

## 호이스팅 (hoisting)
* 변수를 선언 이전에 참조할 수 있는 현상
* var로 선언된 변수는 선언 이전에 참조할 수 있음
* 변수 선언 이전의 위치에서 접근 시 undefined를 반환
* 즉 javascript에서 변수들은 실제 실행시에 코드의 최상단으로 끌어 올려지게 되며 이러한 이유 때문에 var로 선언된 변수는 선언 시에 undefined로 값이 초기화되는 과정이 동시에 일어남
* 반면 let, const는 호이스팅이 일어나면 에러를 발생시킴

<br/>

## 템플릿 리터럴 (Template literals)
* 내장된 표현식을 허용하는 문자열 작성 방식
* ES6+ 부터 지원
* Backtick(``)을 이용하며, 여러 줄에 걸쳐 문자열을 정의할 수도 있고 javascript의 변수를 문자열 안에 바로 연결할 수 있는 이점이 생김
* 표현식은 $와 중괄호 (${expression})로 표기

<br/>

## 반복문 사용시 const 및 let
* for 문
  * for (let i = 0; i < arr.length; i++) {...}의 경우네는 최초 정의한 i를 '재할당'하면서 사용하기 때문에 const를 사용하면 에러 발생
* for...in, for...of
  * 재할당이 아니라 매 반복마다 다른 속성이름이 변수에 지정되는 것이므로 const를 사용해도 에러가 발생하지 않음

<br/>

## NaN을 반환하는 경우
1. 숫자로서 읽을 수 없음
2. 결과가 허수인 수학 계산식
3. 피연산자가 NaN (7** NaN)
4. 정의할 수 없는 계산식 (0*infinity)
5. 문자열을 포함하면서 덧셈이 아닌 계산식('가'/3)

2023.03.14