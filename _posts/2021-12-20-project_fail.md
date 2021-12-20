---
title: "삽질...1"
categories:
  - 프로젝트
tags:
  - 삽질
  
---
Gradle Multi Project 구성으로 프로젝트 시작
블로그를 참고 해서 작업을 하였고 Repository 테스트 도중 
오류 발생
![error](/assets/images/error.png)



java.lang.IllegalStateException: Failed to load ApplicationContext
문구만 보고 @WebAppConfiguration 어노테이션을 붙이면 해결할 수 있다는 글을 보고 시도 해보았지만 실패 했다.
계속 삽질만 하다가 천천히 오류 문구를 확인 해보았다
![error](/assets/images/error1.png)

properties 확인 해보았으며 결국 오타로 인한 삽질 이었다....

spring.jpa.database-platform=org.hibernate.dialect.MYSQL8Dialect

spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect

그래도 해결되어서 다행이다......
