---
title: "[MySQL] programmers : 입양 시각 구하기(1)"
excerpt: "group by"

categories:
  - Programmers
tags:
  - [mysql]

permalink: /programmers/mysql-2/

toc: true
toc_sticky: true

date: 2023-01-30
last_modified_at: 2023-01-30
---

## Problem

<https://school.programmers.co.kr/learn/courses/30/lessons/59041>

<img src="/assets/images/programmers/mysql-2/problem.png" alt="problem"><br/>
<br/>
<img src="/assets/images/programmers/mysql-2/example.png" alt="example"><br/>

## Idea

우선 각 입양 시간에 따라 그룹화하고 9시부터 19시까지의 레코드만을 추출한다. 이후 각 시간대별 레코드의 개수를 count를 통해 세준다.

## Code

```sql
SELECT 
    HOUR(DATETIME) AS HOUR, COUNT(*) AS COUNT
FROM ANIMAL_OUTS
GROUP BY HOUR(DATETIME)
HAVING HOUR BETWEEN 9 AND 19
ORDER BY HOUR;
```

## Comment

