---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-11 09:40
aliases:
  - mappedBy
  - java-jpa-bidirectional-relationship
---
```java
// Instructor.java
@OneToOne(cascade = CascadeType.ALL)
@JoinColumn(name = "instructor_detail_id")
private InstructorDetail instructorDetail;

@OneToMany(mappedBy = "instructor")
private List<Course> courses;


// InstructorDetail.java
@OneToOne(mappedBy = "instructorDetail")
private Instructor instructor;
```
- annotation element in any relationship annotation
- connects the field to the foreign key from another table, allowing a bidirectional relationship between `@Entity` ([java-jpa-entity](java-jpa-entity.md))
- value is the field of the owning entity with the `@JoinColumn` ([java-jpa-joincolumn-annotation](java-jpa-joincolumn-annotation.md)) annotation
- [>] the `InstructorDetail` belongs to an `instructor`
- [>] the `Instructor` belongs to or is assigned to a list of `Course`

useful in allowing a bidirectional relationship between `@Entity`-s