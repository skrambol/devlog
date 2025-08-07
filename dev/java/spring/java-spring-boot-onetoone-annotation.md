---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-07 10:08
alias: java-spring-boot-joincolumn-annotation
---
```java
@OneToOne(cascade = CascadeType.ALL)
@Nullable
@JoinColumn(name = "instructor_detail_id")
private InstructorDetail instructorDetail;
```
- annotation on foreign key field inside `@Entity` ([java-jpa-entity-creation](dev/java/java-jpa-entity-creation.md))
- creates a foreign key field to the `@Entity` table
- simulates/allows a one-to-one mapping similar to a relational database
- `@JoinColumn(name = "foreign_table_id")`
	- specifies the foreign key field on the table

useful in creating one-to-one mapping between two tables in Spring Boot applications