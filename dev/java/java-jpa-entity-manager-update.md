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

e.setField(newValue);
entityManager.merge(e);
```
- `entityManager.merge(updatedObject)`
- can also use [java-jpa-executeupdate](java-jpa-executeupdate.md) to perform updates on multiple rows
- when `primaryKey` is an int and has a value of 0, this instead creates a new entry to the database

useful in performing update operations using JPA EntityManager