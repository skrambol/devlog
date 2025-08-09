---
tags:
  - dev
  - java
  - spring-boot
  - java-jpa
created_at: 2025-07-24 11:05
---
![](../../../attachments/Pasted%20image%2020250724093859.png)
```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Repository;

import jakarta.persistence.EntityManager;

@Repository
public class StudentDAOImpl implements StudentDAO {

	private EntityManager entityManager;

	@Autowired
	public StudentDAOImpl(EntityManager entityManager) {
		this.entityManager = entityManager;
	}

	@Override
	public void save(Student theStudent) {
		entityManager.persist(theStudent);
	}

}

```
- **D**ata **A**access **O**bject is a Java class implementing CRUD methods
- uses a `@Repository` under the hood
	- can be EntityManager or JpaRepository
- `@Repository` connects to a data source, specified in `application.properties` [java-spring-boot-jdbc-application-properties](spring/java-spring-boot-jdbc-application-properties.md)
- think of Controller in MVC
- create DAO interface
	- fill in CRUD method/s
- create DAO implementation
	- add `@Repository` annotation
	- add field for EntityManager
	- inject entityManager in constructor
- implement CRUD methods
- add `@Transactional`
 - to automatically start and end database transactions

useful in creating DAO to connect the `@Entity` [java-jpa-entity](java-jpa-entity.md) to the databse