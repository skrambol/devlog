---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-30 09:36
---
```java
@Service
public class MyServiceImpl implements MyService {
	MyDAO myDAO;

	public class MyServiceImpl(MyDAO myDAO) {
		this.myDAO = myDAO;
	}

	@Transactional
	@Override
	public void transact() {
		myDAO.add();
		myDAO.subtract();
		myDAO.etc();
	}
}

```
- ![](../../../attachments/Pasted%20image%2020250729101237.png) 
- annotation used on Java classes
- usually has a `@Repository` dependency
	- [java-jpa-data-access-object](dev/java/java-jpa-data-access-object.md)
	- or `JpaRepository` ([java-spring-jparepository](java-spring-jparepository.md))
- contains `@Transactional` ([java-spring-transactional-annotation](java-spring-transactional-annotation.md)) methods to encapsulate business processes
- contains business logic or domain logic
	- i still don't fully understand what business logic means
	- business logic for example might be a process wherein multiple db tables are being updated

useful in separating business logic from http controller logic and database logic