---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-16 19:05
aliases:
  - "@ManyToMany"
---
```java
//Course.java
@ManyToMany
@JoinTable(name="course_student", joinColumns=@JoinColumn(name="course_id"), inverseJoinColumns=(name="student_id"))
private List<Student> students;

//Student.java
@ManyToMany(mappedBy = "students")
private List<Course> courses;
```
- annotation on [`@Entity`](dev/java/jpa/java-jpa-entity.md) field
- allows many to many relationship between `@Entity`

useful in annotating `@Entity` fields for a many to many relationship in Java