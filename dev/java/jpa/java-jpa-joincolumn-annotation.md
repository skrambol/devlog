---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-11 09:40
aliases:
  - "@JoinColumn"
---
```java
// Instructor.java
@OneToOne(cascade = CascadeType.ALL)
@JoinColumn(name = "instructor_detail_id")
private InstructorDetail instructorDetail;
```
- creates a foreign key in the `@Entity` ([java-jpa-entity](dev/java/jpa/java-jpa-entity.md))
- specifies the foreign key field on the table if used with the annotation element `name`
- [>] can be read as the `Instructor` has an `instructorDetail`

useful in annotating a field to be a foreign key