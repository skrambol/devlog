---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-12 11:36
aliases:
  - "FetchType"
---
```java
@ManyToOne(fetch = FetchType.Lazy)
```
- annotation element `fetch` inside relationship annotation
- Eager -> retrieves related entities all at once
- Lazy -> only retrieve when needed/accessed
	- needs to be manually retrieved
	- needs to have an existing Hibernate session when related entities are loaded; will throw an error otherwise
		- adding `@Transactional` ([java-spring-transactional-annotation](../spring/java-spring-transactional-annotation.md)) when fetching lazy entities will allow you to fetch it
- defaults
	- `@OneToOne` ([java-jpa-onetoone-annotation](java-jpa-onetoone-annotation.md)) -> eager
	- `@OneToMany` ([java-jpa-onetomany-annotation](java-jpa-onetomany-annotation.md)) -> lazy
	- `@ManyToOne` ([@ManyToOne](java-jpa-manytoone-annotation.md)) -> eager
	- `@ManyToMany` -> lazy

useful in specifying when related entities are fetched (mostly for optimization)