# Functions

<br>

## Function
* 참조 자료형에 속하며 모든 함수는 Function object

<br>

## 함수의 구조
- 함수의 이름
- 함수의 매개변수
- 함수의 body를 구성하는 statement

## 선언식 (function declaration)
```html
function funName () {
  statement
}
```

<br>

## 표현식 (function expression)
```html
const funcName = function () {
  statements
}
```

<br>

## 선언식 예시 
```html
function add (num1, num2) {
  return num1 + num2
}

add(2, 7) // 9
```

<br>

## 표현식 예시
```html
const sub = function (num1, num2) {
  return num1 - num2
}

sub(7, 2) //5
```

<br>

## 함수 표현식 특징
* 함수 이름이 없는 '익명 함수'를 사용할 수 있음
* 선언식과 달리 표현식으로 정의한 함수는 호이스팅 되지 않으므로 코드에서 나타나기 전에 먼저 사용할 수 없음

<br>

## 기본 함수 매개변수 (Default function parameter)
* 값이 없거나 undefined가 전달될 경우 이름 붙은 매개변수를 기본값으로 초기화

<br>

## 나머지 매개변수 (Rest parameters)
* 무한한 수의 인자를 '배열'로 허용하여 가변 함수를 나타내는 방법

<br>

## 화살표 함수 표현식 (Arrow function expressions)
* 함수 표현식의 간결한 표현법

<br>

## 화살표 함수 표현식 작성 순서
1. function 키워드 제거 후 매개변수와 중괄호 사이에 화살표(=>) 작성
2. 함수의 매개변수가 하나 뿐이라면 매개변수의 `()` 제거 가능
3. 함수 본문의 표현식이 한 줄이라면 `()`와 `return` 제거 가능

2023.03.15
