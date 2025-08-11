---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-07 10:08
aliases:
  - "@OneToOne"
---
```java
// Instructor.java
@OneToOne(cascade = CascadeType.ALL)
@Nullable
@JoinColumn(name = "instructor_detail_id")
private InstructorDetail instructorDetail;
```

```java
// InstructorDetail.java
@OneToOne(mappedBy = "instructorDetail")
private Instructor instructor;
```
- annotation on foreign key field inside `@Entity` ([java-jpa-entity](java-jpa-entity.md))
- creates a foreign key field to the `@Entity` table
- simulates/allows a one-to-one mapping similar to a relational database
- allows for a bidirectional relationship if used with `mappedBy` ([java-jpa-mappedby-element](java-jpa-mappedby-element.md)) element

useful in creating one-to-one mapping between two tables in Spring Boot applications