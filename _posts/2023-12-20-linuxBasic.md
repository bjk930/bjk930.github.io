---
layout: single
title: "리눅스 필수 기본 명령어 10가지"
published: true
categories: ubuntu
tags: [linux, ubuntu]
toc: true
---

<br/>
<br/>

## man
<br/>
도움말을 보여준다.
<br/>
<br/>

Ex)&nbsp;ls 명령어에 대한 도움말 보기
```bash
$ man ls
```

<br/>

<hr/>

## pwd (print working directory)
<br/>
현재 위치 경로를 나타낸다.
<br/>
<br/>

Ex)
```bash
$ pwd
```

<br/>

<hr/>

## ls (list)
<br/>
현재 디렉토리에 있는 파일이나 디렉토리의 이름을 나타낸다.
<br/>
<br/>
-a : 숨김 파일과 디렉토리 나타냄<br/>
-l : 파일과 디렉토리 상세 정보 표시<br/>
-r : 파일 정렬 순서 거꾸로 표시<br/>
-t : 파일 작성 시간 순(내림차순)으로 표시<br/>
<br/>

Ex)
```bash
$ ls -al
```

<br/>

<hr/>

## cd (change directory)
<br/>
작업 중인 디렉토리를 변경한다.
<br/>
<br/>
cd &nbsp; .. : 상위 디렉토리로 이동<br/>
cd : 홈 디렉토리로 이동<br/>
cd &nbsp; [절대경로]: 절대경로로 이동<br/>
<br/>

Ex) &nbsp; /user/rem으로 이동
```bash
$ cd /user/rem
```
<br/>
cd &nbsp;[하위 디렉토리] : 하위 디렉토리로 이동<br/>
<br/>

Ex) &nbsp; work로 이동
```bash
$ cd work
```

<br/>

<hr/>

## mkdir (make directory)
<br/>
현재 디렉토리에 하위 디렉토리를 만든다.
<br/>
<br/>

Ex)&nbsp; test 디렉토리 생성
```bash
$ mkdir test
```

<br/>

<hr/>

## rm (remove)
<br/>
디렉토리나 파일을 삭제한다.
<br/>
<br/>
-d : 디렉토리 삭제<br/>
-r : 디렉토리 및 하위 디렉토리와 파일을 모두 삭제
<br/>
<br/>

Ex)
```bash
$ rm -r test
```
 
<br/>

<hr/>

## cp (copy)
<br/>
디렉토리나 파일을 복사한다. 하위 디렉토리가 아니면 절대경로를 입력한다.
<br/>
<br/>

Ex) &nbsp; test1.txt을 test2.txt로 복사
```bash
$ cp test1.txt test2.txt
```
Ex) &nbsp; test.txt를 Directory에 복사
```bash
$ cp test.txt Directory
```
Ex) &nbsp; Dir1을 Dir2에 복사
```bash
$ cp -r Dir1 Dir2
```

<br/>

<hr/>

## mv (move)
<br/>
파일의 이름이나 위치를 변경한다. 하위 디렉토리가 아니면 절대경로를 입력한다.
<br/>
<br/>

Ex) &nbsp;test1.txt를 test2.txt로 이름 변경
```bash
$ mv test1.txt test2.txt
```
Ex) &nbsp;test1.txt를 Directory로 옮기기
```bash
$ mv test1.txt Directory
```

<br/>

<hr/>

## cat (concatenate)
<br/>
파일내용을 확인한다.
<br/>
<br/>

Ex) &nbsp; test1의 내용 확인
```bash
$ cat test1
```

<br/>

<hr/>

## touch
<br/>
크기가 0인 새 파일을 생성한다. 이미 존재하면 생성 날짜를 지금으로 변경한다.
<br/>
<br/>

Ex)
```bash
$ touch test1
```
