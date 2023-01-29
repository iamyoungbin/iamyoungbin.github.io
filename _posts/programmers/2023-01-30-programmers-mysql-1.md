---
title: "[MySQL] programmers : 동명 동물 수 찾기"
excerpt: "group by"

categories:
  - Programmers
tags:
  - [mysql]

permalink: /programmers/mysql-1/

toc: true
toc_sticky: true

date: 2023-01-30
last_modified_at: 2023-01-30
---

## Problem

<https://school.programmers.co.kr/learn/courses/30/lessons/59041>

<img src="/assets/images/programmers/mysql-1/problem.png" alt="problem"><br/>
<br/>
<img src="/assets/images/programmers/mysql-1/example.png" alt="example"><br/>

## Idea

이름이 몇 번 쓰여지는지 알아야하므로 이름에 대해 그룹을 묶고 having으로 쓰인 횟수가 2 이상인 레코드만 추출했다.

## Code

```sql
SELECT NAME, COUNT(*) AS COUNT FROM ANIMAL_INS
GROUP BY NAME
HAVING COUNT >= 2 and NAME is not NULL
ORDER BY NAME;
```

## Comment

group by 사용 시, NULL 또한 함께 집계한다는 사실을 잊지 말자.