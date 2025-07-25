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
entityManager.remove(e);
System.out.println(e);
```
- `entityManager.remove(objectToDelete)`
- deletes the object from the database
- object values is still accessible, if not yet removed from scope
- can also use [java-jpa-executeupdate](java-jpa-executeupdate.md) to perform deletion on multiple rows

useful in performing delete operations using JPA EntityManager