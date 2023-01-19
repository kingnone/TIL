# Python_function

## while
* whil문은 조건식이 참인 경우 반복적으로 코드를 실행

### 1부터 입력받은 정수까지의 총합을 구하는 코드

### while문을 이용한 코드
```
n = int(input("정수를 입력해주세요 > ")

sum = 0
i = 1

while i <= n:
	sum += i
	i += 1

print(f"1부터 {n}까지의 정수 합은 {sum} 입니다.") 
```

### for문을 이용한 코드 
```
target_number = int(input())
result = 0

for n in range(1, target_number+1):
	result = n + result

print(result)
``` 

## Abstraction
- 복잡한 내용을 숨기고, 기능에 집중하여 사용할 수 있음

## 함수
### 함수란?
- 특정한 기능을 하는 코드의 조각(묶음)
- 특정 명령을 수행하는 코드를 매번 다시 작성하지 않고, 필요 시에만 호출하여 간편히 사용

## 함수 정리
- sep=' ' : sep라는 키워드는 기본 값이 space
- end='/n' : end라는 키워드는 기본 값이 개행 
- print 함수는 변환 값이 없습니다.

### 자주 사용하는 함수
- len 객체의 길이를 반환
- sum 합계를 반환
- max 가장 큰 값을 반환
- min 가장 작은 값을 반환

### max 예시
```
numbers = [10, 20, 5]
print(max[numbers]) # 20
print(max(1, 5, 7)) # 7
```
### 수학 관련 함수
- abs 숫자의 절댓값을 반환
- divmod(a, b) 두 수를 받아 몫과 나머지를 반환
- pow 거듭제곱 반환
- round 숫자를 반올림 해준다

### sorted 정렬해주는 함수
```
a = [10, 20, 5]
print(sorted(a)) #[5, 10, 20]
```


### map 함수
* 첫번째 인자 (input)으로 함수를 받아서
* 두번째 인자 (input)인 반복 가능한 객체의 모든 요소에 적용!
```
numbers = ['1', '2', '3']
result = 0
for number in numbers:
    result += int(number)
print(result)

numbers = ['1', '2', '3']
new_numbers = []
for number in numbers:
    new_numbers.append(int(number))
print(new_numbers)
```

2023.01.04