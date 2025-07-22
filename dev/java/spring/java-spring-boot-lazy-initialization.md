---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-22 11:23
aliases:
  - 
---
![](../../../attachments/Pasted%20image%2020250722101740.png)
- class is only initialized when visiting the endpoint
- all Beans ([java-spring-boot-bean](java-spring-boot-bean.md)) are initialized when a Spring Boot application ([java-spring-boot-springbootapplication-annotation](java-spring-boot-springbootapplication-annotation.md)) starts
- introduce lazy initialization by
	- `@Lazy` annotation for specific Bean
		- [java-spring-boot-lazy-annotation](java-spring-boot-lazy-annotation.md)
	- `spring.main.lazy-initialization=true` to be applied to all Beans
		- [java-spring-boot-application-properties-lazy-initialization](java-spring-boot-application-properties-lazy-initialization.md)
- pros
	- faster startup time
- cons
	- config errors will only be thrown during runtime
	- maybe out of memory when creating new beans

useful in applying lazy loading to a Spring Boot application