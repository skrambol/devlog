---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-31 11:01
aliases:
  - "@RepositoryResource"
---
```java
@RepositoryResource(path="new-path")
public interface MyRepository extends JpaRepository<T, K> {}
```
- annotation placed on `@Repository` ([java-spring-repository-annotation](java-spring-repository-annotation.md))
- replaces default path `entitys` from Spring Data REST ([java-spring-boot-data-rest](java-spring-boot-data-rest.md))

useful in correcting plural form of noun or having custom path