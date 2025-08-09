---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-07 10:08
aliases:
  - "@OneToOne"
  - java-spring-boot-onetoone-annotation
  - java-jpa-joincolumn-annotation
  - java-jpa-mappedby-element
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
- `@JoinColumn(name = "foreign_table_id")`
	- specifies the foreign key field on the table
	- creates a foreign key in the `@Entity`
- `@OneToOne(mappedBy = "instructorDetail")`
	- allows for a bidirectional one-to-one relationship
	- located in the non-owning `@Entity`
	- the value of the element ([java-annotation-elements](../java-annotation-elements.md)) is the field name from the owning `@Entity`

useful in creating one-to-one mapping between two tables in Spring Boot applications