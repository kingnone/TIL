# 사용자 정의 함수 

## 함수 기본 구조
- 선언과 호출
- 입력
- 범위
- 결과값

## 선언&호출
- 함수의 선언은 def 키워드를 활용함
- 들여쓰기를 통해 Function body(실행될 코드 블록)를 작성함
- 함수는 parameter를 넘겨줄 수 있음
- 함수는 동작 후에 return을 통해 결과값을 전달함

## 선언 및 호출
- 함수는 함수명()으로 호출

</br>

# 함수의 결과 값 (output)

## return
- 함수는 반드시 값을 하나만 return한다
- 명시적인 return이 없는 경우에도 None을 반환한다
- 함수는 return과 동시에 종료된다

## return vs print
- return은 함수 안에서 값을 반환하기 위해 사용되는 키워드
- print는 출력을 위해 사용되는 함수

</br>

# 함수의 입력 (input)

## Parameter vs Argument
- Parameter : 함수를 실행할 때, 함수 내부에서 사용되는 식별자
- Argument 함수를 호출 할 때, 넣어주는 값

## argument 

## argument란?
- 함수 호출 시 함수의 parameter를 통해 전달되는 값
- Argument는 소괄호 안에 할당 func_name(argument)
- 필수 Argument : 반드시 전달되어야하는 argument
- 선택 Argument : 값을 전달하지 않아도 되는 경우는 기본 값이 전달

## positional arguments
- 기본적으로 함수 호출 시 Argument는 위치에 따라 함수 내에 전달 됨

## keyword arguments
- 직접 변수의 이름으로 특정 argument를 전달할 수 있음
- keyword Argument 다음에 positional argument를 활용할 수 없음

## Default Arguments Values
- 기본값을 지정하여 함수 호출 시 argument 값을 설정하지 않도록 함

## 정해지지 않은 개수의 arguments
- 여러 개의 positional argument를 하나의 필수 parameter로 받아서 사용
- argument들은 튜플로 묶여 처리되며, parameter에 * 를 붙여 표현

```
def add(*args):
	for arg in args:
	print(arg)
```

## 정해지지 않은 개수의 keyword arguments
- 함수가 임의의 개수 argumet를 keyword argument로 호출될 수 있도록 지정
- argument들은 딕셔너리로 묶여 처리되며, parameter에 **를 붙여 표현

```
def family(**kwargs):
	for key, value in kwargs:
	   print(key, ":", value)
family(father='John', mother='Jane', me='John Jr.')
```

</br>

# 함수의 범위 (Scope)

## 함수의 scope
- 함수는 코드 내부의 local scope를 생성하며, 그 외의 공간인 global scope로 구분

## 객체 수명주기
- 객체는 각자의 수명주기가 존재

## 이름 검색 규칙 (Name Resolution)
- 파이썬에서 사용되는 이름(식별자)들은 이름공간(namespace)에 저장되어 있음
- 아래와 같은 순서로 이름을 찾아나가며, LEGB Rule이라고 부름
- Local scope : 함수
- Enclosed scope : 특정 함수의 상위 함수
- Global scope : 함수 밖의 변수, import 모듈
- Built-in scope : 파이썬 안에 내장되어 있는 함수 또는 속성
- 즉, 함수 내에서는 바깥 scope의 변수에 접근 가능하나 수정은 할 수 없음

2023.01.10