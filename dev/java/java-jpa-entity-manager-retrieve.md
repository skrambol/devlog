---
tags:
  - dev
  - java
  - spring-boot
  - java-jpa
created_at: 2025-07-25 11:04
---
```java
// usually in DAO Implementation
MyEntity e = entityManager.find(MyEntity.class, primaryKey);
```
- `entityManager.find(MyEntity.Class, primaryKey)`
- returns the object having `primaryKey`
- can also use [java-jpa-getresultlist](java-jpa-getresultlist.md) to retrieve rows

useful in performing retrieve operations using JPA EntityManager