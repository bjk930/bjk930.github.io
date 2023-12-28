---
layout: single
title: "Git conflict 해결하기"
published: true
categories: git
tags: git
toc: true
---


      

## 방법1: 기존 작업 add commit 후 master branch pull로 가져옴.(완성본) 그 다음 master로 push 

ex)
1. git pull origin develop
2. git checkout feature-A
3. git merge develop
4. 문제요소 조정
5. git push -u origin feature-A
  
## 방법2: 깃허브 홈페이지 pull requests의 경우, resolve conflicts 사용
