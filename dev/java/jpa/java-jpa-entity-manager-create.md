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
MyEntity newEntity = new MyEntity(val1, val2, val3);
entityManager.persists(newEntity);
```
- `entityManager.persists(new MyEntity())`
- can also use [java-jpa-entity-manager-createqeury](java-jpa-entity-manager-createqeury.md) to retrieve rows

useful in performing create operations using JPA EntityManager