---
title: ".gitignore db.sqlite3가 적용되지 않을 때"
excerpt: ""

categories:
  - Git
tags:
  - [git, django]

permalink: /git/20230419_dbsqlite3/

toc: true
toc_sticky: true

date: 2023-04-19
last_modified_at: 2023-04-21
---

.gitignore에 db.sqlite3와 db.sqlite3-journal을 추가했음에도 무시되지 않을 때

1. .gitignore에 *.sqlite3 추가
2. git rm –cached db.sqlite3 실행
3. commit