---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-30 10:53
aliases:
  - JpaRepository
---
```java
import org.springframework.data.jpa.repository.JpaRepository;

public interface EmployeeRepository extends JpaRepository<Employee, Integer> {

}
```
- automagically adds common CRUD methods on a given `@Entity` ([java-jpa-entity](../jpa/java-jpa-entity.md))
- to be used instead of DAO ([java-jpa-data-access-object](../jpa/java-jpa-data-access-object.md)) since it removes most boilerplate codes
	- no need to create DAO interface
	- no need to create DAO implementation/class
- to be injected as a dependency on `@Service` ([java-spring-service-annotation](java-spring-service-annotation.md))
- no need to create `findAll`, `findById`, `save`, etc. methods

useful in creating common CRUD methods for an `@Entity`