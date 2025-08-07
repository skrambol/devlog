---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter
created_at: 2025-07-31 10:49
---
```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-data-rest</artifactId>
</dependency>
```
- automagically adds REST endpoints depending on the entity of the `@Repository` ([java-spring-repository-annotation](dev/java/spring/java-spring-repository-annotation.md))
	- used `JpaRepository` ([java-spring-jparepository](dev/java/spring/java-spring-jparepository.md)) in spring boot udemy
- only needs `@Entity` ([java-jpa-entity-creation](../java-jpa-entity-creation.md)) and `@Repository`
- no need for `@RestController` ([java-spring-boot-restcontroller](java-spring-boot-restcontroller.md))
- response is HATEOS (hypermedia as the engine of application state)
	- response has links for self, other entities, next page, last page, etc.
- default endpoints are prefixed by entity name added with s
- `GET /entitys`
- `POST /entitys`
- `PUT /entitys/:id`
- `PATCH /entitys/:id`
- `DELETE /entitys/:id`

useful in automatically creating endpoints for a Spring Boot Repository