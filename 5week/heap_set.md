# 힙(Heap)&셋(Set)

<br/>

## 힙 (Heap)
- 우선순위 큐는 우선순위를 기준으로 가장 우선순위가 높은 데이터가 가장 먼저 나가는 방식

### 우선순위 큐
- 순서가 아닌 우선순위를 기준으로 가져올 요소를 결정하는 큐
1. 가중치가 있는 데이터
2. 작업스케줄링
3. 네트워크

### 우선순위 큐를 구현하는 방법
- 배열(Array)
- 힙(Heap)

### 힙의 특징
- 최대값 또는 최소값을 빠르게 찾아내도록 만들어진 데이터 구조
- 완전 이진 트리의 형태로 느슨한 정렬 상태를 지속적으로 유지 한다
- 힙 트리에서 중복 값을 허용한다

### 힙은 언제 사용
- 데이터가 지속적으로 정렬되야 하는 경우
- 데이터 삽입/삭제가 번번할때

### 파이썬의 힙 모듈
- minheap(최소 힙)으로 구현되어 있음(가장 작은 값이 먼저 온다)
- 삽입, 삭제, 수정, 조회 연산의 속도가 리스트보다 빠르다

<br/>

## 셋(Set)
- 수학에서 집합을 나타내는 데이터 구조로 python에서는 기본적으로 제공되는 데이터 구조

### 셋은 언제 사용  
- 데이터의 중복이 없어야 할 때
- 정수가 아닌 데이터의 삽입/삭제/탐색이 빈번히 필요할때

2023.01.27