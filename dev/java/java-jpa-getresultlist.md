---
tags:
  - dev
  - java
  - spring-boot
  - java-jpa
created_at: 2025-07-25 11:10
---
```java
List<MyEntity> list = entityManager.createQuery("FROM Entity WHERE field = :value", MyEntity.class)
	.setParameter("value", param1)
	.getResultList();
```
- returns a `java.util.List` of `MyEntity`

useful in retrieving multiple rows of data