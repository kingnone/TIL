# 깊이 우선탐색(DFS) vs 너비 우선탐색(BFS)

## 그래프 탐색 알고리즘이란?
* 시작 정점에서 간선을 타고 이동할 수 있는 모든 정점을 찾는 알고리즘

## 깊이 우선탐색 (DFS)
* 시작 정점으로부터 갈 수 있는 하위 정점까지 가장 깊게 탐색하고, 더 이상 갈 곳이 없다면 마지막 갈림길로 돌아와서 다른 정점을 탐색하며 결국 모든 정점을 방문하는 순회 방법

## 깊이 우선탐색 특징
* 모든 정점을 방문할 때 유리함 즉 경우의 수, 순열과 조합 문제에서 많이 사용함
* 너비 우선탐색에 비해 코드 구현이 간단
* 단, 모든 정점을 방문할 필요가 없거나 최단 거리를 구하는 경우에는 너비 우선탐색이 유리

## 깊이 우선탐색 구현
```python
n = len(graph)
visited = [False] * n

start = 0
stack = [start]
visited[start] = True

while stack:
  cur = stack.pop()

  for adj in graph[cur]:
    if not visited[adj]:
      visited[adj] = True
      stack.append(adj)
```
