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


java.lang.IllegalStateException: Failed to load ApplicationContext
문구만 보고 @WebAppConfiguration 어노테이션을 붙이면 해결할 수 있다는 글을 보고 시도 해보았지만 실패 했다.
계속 삽질만 하다가 다시 오류 문구를 확인 해보았다

Caused by: org.hibernate.boot.registry.selector.spi.StrategySelectionException: Unable to resolve name [org.hibernate.dialect.MYSQL8Dialect] as strategy [org.hibernate.dialect.Dialect]
	at org.hibernate.boot.registry.selector.internal.StrategySelectorImpl.selectStrategyImplementor(StrategySelectorImpl.java:156)
	at org.hibernate.boot.registry.selector.internal.StrategySelectorImpl.resolveStrategy(StrategySelectorImpl.java:239)
	at org.hibernate.boot.registry.selector.internal.StrategySelectorImpl.resolveDefaultableStrategy(StrategySelectorImpl.java:183)
	at org.hibernate.boot.registry.selector.internal.StrategySelectorImpl.resolveDefaultableStrategy(StrategySelectorImpl.java:170)
	at org.hibernate.boot.registry.selector.internal.StrategySelectorImpl.resolveStrategy(StrategySelectorImpl.java:164)
	at org.hibernate.engine.jdbc.dialect.internal.DialectFactoryImpl.constructDialect(DialectFactoryImpl.java:74)
	at org.hibernate.engine.jdbc.dialect.internal.DialectFactoryImpl.buildDialect(DialectFactoryImpl.java:51)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.initiateService(JdbcEnvironmentInitiator.java:138)
	at org.hibernate.engine.jdbc.env.internal.JdbcEnvironmentInitiator.initiateService(JdbcEnvironmentInitiator.java:35)
	at org.hibernate.boot.registry.internal.StandardServiceRegistryImpl.initiateService(StandardServiceRegistryImpl.java:101)
	at org.hibernate.service.internal.AbstractServiceRegistryImpl.createService(AbstractServiceRegistryImpl.java:263)

properties 확인 해보았으며 결국 오타로 인한 삽질 이었다....

spring.jpa.database-platform=org.hibernate.dialect.MYSQL8Dialect

spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect

그래도 해결되어서 다행이다......
