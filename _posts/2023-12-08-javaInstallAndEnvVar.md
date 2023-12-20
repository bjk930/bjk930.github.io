---
layout: single
title: "리눅스 우분투 오픈JDK 설치 및 환경변수 설정"
published: true
categories: java
tags :java
---

<br/>
<br/>

## 1. apt update, upgrade

```bash
$ sudo apt update
$ sudo apt upgrade
```

<br/>

## 2. 오픈JDK 설치

```bash
$ sudo apt install openjdk-[버전번호]-jre
$ sudo apt install openjdk-[버전번호]-jdk
```

<br/>

## 3. 설치 확인

```bash
$ java -version
$ javac -version
```

<br/>

윈도우에서는 환경변수와 path 입력을 해야 버전이 확인되었는데
<br/>
우분투는 자바를 설치하자마자 버전이 확인되었다.
<br/>

```bash
$ which java
$ which javac
```
를 입력하면 심볼릭 링크가 나온다.
<br/>
/etc에 가서

```bash
$ echo $PATH
```
를 입력하면 심볼릭 링크가 path에 있는 것을 볼 수 있다.
```bash
$ update-alternatives --display javac
```
를 입력하면 링크가 되어 있음을 확인할 수 있다.
<br/>

`심볼릭 링크가 없다면 update-alternatives --install을 통해 심볼릭 링크를 만드는 방법과 윈도우처럼 Path를 설정하는 방법이 있다.`

<br/>

## 4. JAVA_HOME 변수 생성
```bash
/etc$ sudo vi environment
```
environment파일에 JAVA_HOME 변수 입력
```bash
JAVA_HOME="/usr/lib/jvm/java-[버전숫자]-openjdk-amd64"
```
i를 눌러 편집모드로 들어간 뒤, 기존 PATH 위에 변수 생성, esc 후 shift+colon으로 명령모드 변경, wq로 저장
<br/>

```bash
$ source /etc/environment
```
를 입력하여 environment 변경내역 적용
<br/>

```bash
$ echo $JAVA_HOME
```
를 입력하여 변경여부 확인

`JAVA_HOME 변수를 사용하는 곳이 있을 수 있으니 설정한다.`

## 5. 완료

## 6. 번외 (3번의 PATH 설정하기)

<br/>
<br/>
자바 파일을 만들어 main메소드가 작동하는 것을 확인했다.
추후, PATH 설정을 안해서 문제가 발생한다면, 왜 문제가 발생했는지 알아보고 해결하기 위해 번외를 준비했다.
```bash
$ vi /etc/profile
```
최하단에 아래의 내용 입력
```bash
export JAVA_HOME=/usr/lib/jvm/java-[버전번호]-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
export CLASSPATH=$CLASSPATH:$JAVA_HOME/jre/lib/ext:$JAVA_HOME/lib/tools.jar
```
저장
```bash
$ source /etc/profile
```
