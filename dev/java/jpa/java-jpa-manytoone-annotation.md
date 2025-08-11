---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-11 09:32
aliases:
  - "@ManyToOne"
---
```java
//Course.java
@ManyToOne(cascade = {}, fetch = ...)
@JoinColumn(name = "instructor_id")
private Instructor instructor;
```
- annotation for a field inside the owning `@Entity` ([java-jpa-entity](dev/java/jpa/java-jpa-entity.md))
- the `@Entity` has a many to one relationship to the foreign key
- [>] many `Course` can be assigned to one `Instructor`

useful in annotating a field to have a many to one relationship to the `@Entity`