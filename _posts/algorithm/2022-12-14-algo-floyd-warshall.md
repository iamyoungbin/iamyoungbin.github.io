---
title: "플로이드-워셜(Floyd-Warshall) 알고리즘"
excerpt: "최단 경로 알고리즘의 한 종류인 플로이드-워셜 알고리즘에 대해서 알아보자"

categories:
  - Algorithm
tags:
  - [algorithm]

permalink: /algorithm/floyd-warshall/

toc: true
toc_sticky: true

date: 2022-12-14
last_modified_at: 2022-12-14
---

## Floyd-Warshall 최단 경로 알고리즘

Floyd-Warshall 알고리즘은 그래프에 존재하는 모든 정점 사이의 최단 경로를 한번에 모두 찾아주는 알고리즘이다.

다익스트라 알고리즘이 하나의 출발 정점에서부터 다른 모든 정점까지의 최단 거리를 구하는 것과 달리, 플로이드-워셜 알고리즘은 모든 정점간의 최단 거리를 구할 수 있다. 또한, 플로이드-워셜 알고리즘은 음의 가중치를 가지는 그래프에서도 사용할 수 있다.

## 동작 방식

Floyd-Warshall 알고리즘은 2차원 배열을 이용하여 3중 반복을 하는 루프로 구성되어 있다. 먼저, 그래프의 임의의 두 개의 정점 i, j에 따라 정점간 가중치를 저장하는 인접 행렬 weight를 다음과 같이 구성한다.

1.	i == j 이면, weight[i][j] = 0
2.	i와 j 사이에 간선이 존재하지 않으면 weight[i][j] = INF
3.	i와 j 사이에 간선이 존재하면 weight[i][j]는 해당 간선의 가중치가 된다.

## 구현

Floyd-Warshall 알고리즘의 의사 코드는 다음과 같다.

```c
floyd(G):
	for k = 0 to n-1:
		for i = 0 to n-1:
			for j = 0 to n-1:
				weight[i][j] = min(weight[i][j], weight[i][k] + weight[k][j])
```

알고리즘을 설명하기 위하여 A[i][j]를 현재 까지 구해진 정점 i에서 j까지의 최단 거리라고 하자. 그래프 내의 임의의 노드 k를 거치는 거리인 A_k[i][j]와 A[i][i]를 비교하여 더 작은 쪽을 A[i][j]로 설정하는데, 이를 그래프 내의 모든 노드들을 대상으로 수행한다.

## 시간 복잡도

최대 n번 실행되는 루프문이 3번 중첩되므로, 플로이드-워샬 알고리즘의 시간 복잡도는 O(n^3)이 되고, 정점의 수가 적을수록 유리하다.

## 참조

천인국,공용해,하상호. 『C언어로 쉽게 풀어쓴 자료구조』. 생능출판, 2017.