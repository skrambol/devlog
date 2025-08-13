---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-13 11:19
aliases:
  - "@Query"
---
```java
//InstructorRepository.java
@Query("SELECT i FROM Instructor i JOIN FETCH i.courses JOIN FETCH i.instructorDetail")
public Instructor getInstructorProfile();
```
- annotation on `JpaRepository` ([java-spring-jparepository](dev/java/spring/java-spring-jparepository.md)) method
- used in creating custom query for `JpaRepository`
- example use case in [java-jpa-join-fetch-query](java-jpa-join-fetch-query.md)

useful in creating custom query for `JpaRepository`