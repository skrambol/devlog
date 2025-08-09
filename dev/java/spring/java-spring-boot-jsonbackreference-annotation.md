---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-09 17:08
aliases:
  - "@JsonBackReference"
---
```java
//Instructor.java

@OneToOne(cascade = CascadeType.ALL)
@Nullable
@JoinColumn(name = "instructor_detail_id")
@JsonBackReference
private InstructorDetail instructorDetail;
```
- annotates the field in the owning `@Entity` ([java-jpa-entity](../jpa/java-jpa-entity.md))
- translates to `Instructor` has-a `InstructorDetail`

useful to display a has-a relationship between `@Entity` relationships