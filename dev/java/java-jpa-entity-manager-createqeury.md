---
tags:
  - dev
  - java
  - spring-boot
  - java-jpa
created_at: 2025-07-25 11:07
---
```java
entityManager.createQuery("FROM Entity WHERE field = :value", entity.class)
	.setParameter("value", param1);
```
- can be used to retrieve multiple rows of data [java-jpa-getresultlist](java-jpa-getresultlist.md)
- can be used to update/delete multiple rows of data [java-jpa-executeupdate](java-jpa-executeupdate.md)

useful in creating custom query for JPA