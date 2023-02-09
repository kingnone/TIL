# 이차원 리스트

## 이차원 리스트란?
* 리스트를 원소로 가지는 리스트
* 이차원 리스트는 행렬이다

## 특정 값으로 초기화 된 이차원 리스트 만들기

### 직접 작성 (4 x 3 행렬)
```python
matrix = [[0, 0, 0], [0, 0, 0], [0, 0, 0], [0, 0, 0]]

matrix2 = [
  [0, 0, 0],
  [0, 0, 0],
  [0, 0, 0],
  [0 ,0, 0]
]
```

### 반복문으로 작성 (100 x 100)
```python
matrix = []

for _ in range(100):
  matrix.append([0] * 100)
```

### 리스트 컴프리헨션으로 작성 (n x m 행렬)
```python
n = 4 #행
m = 3 #열

matrix = [[0] * m for _ in range(n)]

print(matrix)
>>>[[0, 0, 0], [0, 0, 0], [0, 0, 0], [0, 0, 0]]
```

## 이차원 리스트에 담긴 모든 원소를 출력하고 싶다면?

### 인덱스를 통해 각각 출력하면 가능하다
```python
matrix = [
  [1, 2, 3, 4],
  [5, 6, 7, 8],
  [9, 0, 1, 2]
]

print(matrix[0][0], matrix[0][1], matrix[0][2], matrix[0][3])
print(matrix[1][0], matrix[1][1], matrix[1][2], matrix[1][3])
print(matrix[2][0], matrix[2][1], matrix[2][2], matrix[2][3])

>>> 1 2 3 4
>>> 5 6 7 8
>>> 9 0 1 2
```

### 이중 for문을 이용한 행 우선 순회
```python
matrix = [
  [1, 2, 3, 4], 
  [5, 6, 7, 8],
  [9, 0, 1, 2]
]

for i in range(3):
  for j in range(4):
    print(matrix[i][j], end=" ")
  print()

>>> 1 2 3 4 
>>> 5 6 7 8
>>> 9 0 1 2
```

### 이중 for문을 이용한 열 우선 순회
```python
matrix = [
  [1, 2, 3, 4], 
  [5, 6, 7, 8],
  [9, 0, 1, 2]
]

for i in range(4):
  for j in range(3):
    print(matrix[j][i], end=" ")
  print()

>>> 1 5 9
>>> 2 6 0
>>> 3 7 1
>>> 4 8 2
```
## 전치 (transpose)
* 행렬의 행과 열을 서로 맞바꾸는 것을 의미

```python
matrix = [
  [1, 2, 3, 4],
  [5, 6, 7, 8],
  [9, 0, 1, 2]
]

transposed_matrix = [[0] * 3 for _ in range(4)]

for i in range(4):
  for j in range(3):
    transposed_matrix[i][j] = matrix[j][i]

"""
transposed_matrix = [
  [1, 5, 9],
  [2, 6, 0],
  [3, 7, 1],
  [4, 8, 2]
]
"""
```

## 회전
### 왼쪽으로 90도 회전
```python
matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]

n = 3
rotated_matrix = [[0] * n for _ in range(n)]

for i in range(n):
  for j in range(n):
    rotated_matrix[i][j] = matrix[j][n-i-1]
```

### 오른쪽으로 90도 회전하기
```python
matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]

n = 3
rotated_matrix = [[0] * n for _ in range(n)]

for i in range(n):
  for j in range(n):
    rotated_matrix[i][j] = matrix[j][n-j-1]
```

2023.01.30