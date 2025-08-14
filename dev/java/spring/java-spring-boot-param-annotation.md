---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-13 11:24
aliases:
  - "@Param"
---
```java
//InstructorRepository.java
@Query("SELECT i FROM Instructor i JOIN FETCH i.courses JOIN FETCH i.instructorDetail where i.id = :id")
public Instructor getInstructorProfile(@Param("id") int idName);
```
- annotation on function arguments
- used to pass parameterized values in custom query (`@Query` ([java-spring-boot-query-annotation](java-spring-boot-query-annotation.md)))
- take not that the value inside annotation is to be used in custom query, not the variable name
- example use case in [java-jpa-join-fetch-query](../jpa/java-jpa-join-fetch-query.md)

useful in having parametrized value for custom queries in `JpaRepository`