---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-16 19:13
aliases:
  - "@JoinTable"
---
```java
//Course.java
@ManyToMany
@JoinTable(name="course_student", joinColumns=@JoinColumn(name="course_id"), inverseJoinColumns=(name="student_id"))
private List<Student> students;
```
- annotation on the [`@ManyToMany`](java-jpa-manytomany-annotation.md) field of an [`@Entity`](dev/java/jpa/java-jpa-entity.md)
	- `name` -> name of the table
	- [java-jpa-joincolumns-element](java-jpa-joincolumns-element.md)
	- [java-jpa-inversejoincolumns-element](java-jpa-inversejoincolumns-element.md)

useful in specifying the database table to be used for the many to many relation for Java