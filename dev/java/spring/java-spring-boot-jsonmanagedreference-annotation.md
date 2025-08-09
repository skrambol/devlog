---
tags:
  - dev
  - java
  - spring-boot
aliases:
  - "@JsonManagedReference"
created_at: 2025-08-09 17:08
---
```java
//InstructorDetail.java

@OneToOne(mappedBy = "instructorDetail", cascade = { CascadeType.DETACH, CascadeType.MERGE, CascadeType.PERSIST, CascadeType.REFRESH })
@JsonManagedReference
private Instructor instructor;
```
- annotates the field in the non-owning `@Entity` ([java-jpa-entity](../jpa/java-jpa-entity.md))
- translates to `InstructorDetail` belongs-to `Instructor`

useful to display a belongs-to relationship between `@Entity` relationships