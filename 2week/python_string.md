# Python

## 객체(Object)를 활용하기 이해 Type과 연산자

## 제어문
### 제어문이란
- 파이썬은 기본적으로 위에서부터 아래로 순차적으로 명령을 수행
- 특정 상황에 따라 코드를 선택적으로 
- 제어문은 순서도로 표현 가능

## 조건문
- 조건문은 참/거짓을 판단할 수 있는 조건식과 함께 사용 
### 기본 형식
- expression에는 참/거짓에 대한 조건식
- 조건이 참인 경우 이후 들여쓰기 되어있는 코드 블럭을 실행
- 이외의 경우 else 이후 들여쓰기 되어 있는 코드 블럭을 실행

## 복수 조건문
```
if <expression>:
  #code block
elif <expressio>:
  #code block
else:
  #code block
```

## 중첩 조건문
```
if <expression>:
  #code block
  if <expression>:
    #code block
else:
  #code block
```

### 짝수홀수 여부 출력
```
num = input("수를 입력 해주세요 > ")

if num % 2 == 0:
    print("짝수입니다.")
else
    print("홀수입니다.")
```

### 미세먼지 농도에 따른 
```
dust = 80

if dust > 150:
    print("매우나쁨")
elif dust > 80:
    print("나쁨")
elif dust > 30:
    print("보통")
else:
    print("좋음")
print("미세먼지 확인 완료")
```
## 레인지(Range)
- 숫자의 시퀀스를 나타내기 위해 사용
- 변경 불가능하며, 반복 가능함
- range(start, stop, step)

## 반복문
- 특정 조건을 도달할 때까지, 계속 반복되는 일련의 문장

## While 문
- 종료조건에 해당하는 코드를 통해 반복문을 종료시켜야 함

## For 문
- 반복가능한 객체를 모두 순회하면 종료 (별도의 종료조건이 필요 없음)

## 반복 제어
- break, continue, for-else

2023.01.03