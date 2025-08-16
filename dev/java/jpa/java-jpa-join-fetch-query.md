---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-13 11:13
aliases:
  - "JOIN FETCH"
---
```java
//InstructorRepository.java
@Query("SELECT i FROM Instructor i JOIN FETCH i.courses JOIN FETCH i.instructorDetail where i.id = :id")
public Instructor getInstructorProfile(@Param("id") int idName);
```
- fetches related entities, especially if `FetchType` ([java-jpa-fetchtype-element](java-jpa-fetchtype-element.md)) is Lazy
- remember this uses JPA query language ([java-jpa-query-language](java-jpa-query-language.md))

useful in fetching related entities in Spring Boot applications especially if `FetchType` is Lazy