---
layout: single
title: "깃 설치 및 환경설정"
published: true
categories: git
tags: [git, ssh, github]
---


      

## 1. 깃 설치

```bash
$ sudo apt install git
```

## 2. 깃 설치 확인

```bash
$ git --version
```

## 3. 아이디, 이메일 주소 설정

```bash
$ git config --global user.name "[깃허브 아이디]"
$ git config --global user.email "[깃허브 이메일 주소]"
```

## 4. 아이디, 이메일 주소 설정 확인

```bash
$ git config --list
```

## (선택사항) SSH

### 1. SSH key 생성 여부를 확인한다.

<br/>

```bash
$ ls -al ~/.ssh
```

<br/>

### 2. SSH key를 생성한다.

<br/>

$ ssh-keygen -t(타입) [rsa, ed25519 등의 원하는 암호화 방식] -C(커멘트) "[깃허브 이메일 주소]"
```bash
$ ssh-keygen -t ed25519 -C "[깃허브 이메일 주소]"
```

<br/>

Enter file in which to save the key : 저장위치 설정
<br/>
Enter passphrase (empty for no passphrase) : 비밀번호 설정
<br/>
Enter same passphrase again : 비밀번호 재입력

### 3. /home/[사용자명]/.ssh/[암호타입].pub의 내용을 복사한다.
### 4. 깃허브 Settings 메뉴에서 New SSH key를 통해 SSH key를 등록한다.
