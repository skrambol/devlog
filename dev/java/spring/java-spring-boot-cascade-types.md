---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-07 10:03
---
```java
@OneToOne(cascade = CascadeType.ALL)
@Nullable
@JoinColumn(name = "instructor_detail_id")
private InstructorDetail instructorDetail;
```
- applied as element ([java-annotation-elements](../java-annotation-elements.md)) to related fields/table inside `@Entity` ([java-jpa-entity-creation](dev/java/java-jpa-entity-creation.md))
- by  default, no cascade operations

![](../../../attachments/Pasted%20image%2020250806101450.png)
- PERSIST
- REMOVE
- REFRESH
- DETACH
- MERGE
- ALL

useful in cascading operations for related `@Entity`-s in Spring Boot