---
layout: single
title: "Git branch 만들기 및 master branch protect"
published: true
categories: git
tags: git
toc: true
---


## 1. 로컬에서 branch 만들기

```bash
$ git push --set-upstream origin [브랜치명]
```

## 2. master branch protect
1. repository 화면에서 protect this branch 클릭
2. Lock branch(마스터로 직접 깃푸쉬 금지)와 Require a pull request before merging(병합 전 허락요구) 선택
3. create 클릭


