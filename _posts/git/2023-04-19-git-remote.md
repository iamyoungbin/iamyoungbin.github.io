---
title: "로컬 Git 저장소와 GitHub 저장소와 연동하기"
excerpt: ""

categories:
  - Git
tags:
  - [git]

permalink: /git/20230419_remote/

toc: true
toc_sticky: true

date: 2023-04-19
last_modified_at: 2023-04-19
---

## 로컬 Git 저장소 초기화 후 연동하기

```
git init
git add.
git commit -m "frist commit"
git branch -M main  # 현재 브랜치를 강제로 main 브랜치로 이동.
git remote add origin 원격저장소 주소
git push -u origin main
```

<hr>

## 로컬 Git 정보를 유지하면서 연동하기

```
git remote add origin 원격저장소 주소
git branch -M main
git push -u origin main
```

<hr>

## git remote: Invalid username or password 오류

GitHub로부터 토큰을 발급받아 유저 정보를 다시 연결해야 한다.

### 토큰 발급 방법

1. GitHub > 마이페이지 팝업에서 Settings > Developer settings > Personal access tokens
2. Generate new token을 눌러 토큰 발급
3. 토큰번호 복사

### 터미널

```
git remote remove origin # 기존에 리모트 되어있던 레포지토리 주소 제거
git remote add origin https://계정이름:토큰번호@github.com/레포지토리 주소
```

이 때, 레포지토리 주소는 github.com 이후의 주소를 쓰면 된다.
만약, 기존 레포지토리의 주소가 github.com/abcd/new_rep 라면 레포지토리의 주소로 abcd/new_rep를 입력한다.