---
tags:
  - dev
  - java
  - spring-boot
  - java-jpa
created_at: 2025-07-25 11:12
---
```java
int num_updated = entityManager.createQuery("UPDATE FROM Entity SET field = 'value'", MyEntity.class)
	.executeUpdate();
	
int num_deleted = entityManager.createQuery("DELETE FROM Entity", MyEntity.class)
	.executeUpdate();
```
- returns the number of rows updated
- [??] possible to use `INSERT INTO` as well?

useful in