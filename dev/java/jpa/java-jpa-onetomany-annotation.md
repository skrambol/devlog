---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-11 10:47
aliases:
  - "@OneToMany"
---
```java
//Instructor.java
@OneToMany(mappedBy = "instructor")
private List<Course> courses;
```
- annotation for a field inside the non-owning `@Entity` ([java-jpa-entity](dev/java/jpa/java-jpa-entity.md))
- the `@Entity` has a one to many relationship to the field
- allows for a bidirectional relationship between `@Entity`, specifically for `@ManyToOne` ([java-jpa-manytoone-annotation](java-jpa-manytoone-annotation.md))
- [>] an `Instructor` is assigned to multiple `Course`

useful in creating a bidirectional relationship between `@ManyToOne` and `@OneToMany` annotated fields