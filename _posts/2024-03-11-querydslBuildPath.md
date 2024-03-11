---
layout: single
title: "STS4 그래들 프로젝트 스프링부트 버전3 Querydsl 설정'"
published: true
categories: failDiary
tags: [failDiary, java]
---

<br/>
*build.gradle*
<br/>


```bash
//querydsl 설정 추가
	implementation 'com.querydsl:querydsl-jpa:5.0.0:jakarta'
	annotationProcessor "com.querydsl:querydsl-apt:${dependencyManagement.importedProperties['querydsl.version']}:jakarta"
	annotationProcessor "jakarta.annotation:jakarta.annotation-api"
	annotationProcessor "jakarta.persistence:jakarta.persistence-api"
```

```bash
// Querydsl 설정부
def generated = 'src/main/generated'

// querydsl QClass 파일 생성 위치를 지정
tasks.withType(JavaCompile) {
	options.getGeneratedSourceOutputDirectory().set(file(generated))
}

// java source set 에 querydsl QClass 위치 추가
sourceSets {
	main.java.srcDirs += [ generated ]
}

// gradle clean 시에 QClass 디렉토리 삭제
clean {
	delete file(generated)
}
```

<br/>
refresh gradle project와 gradle task에서 build를 해준다. 그러면 q클래스가 생성되었을 것이다. sts를 종료 후 다시 켜면 package explorer에 generated 파일이 나타난다.
나타나지 않으면 직접 java build path에 가서 source에 generated 폴더를 추가해 주자.
