---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-23 10:46
---
- Bean ([java-spring-boot-bean](dev/java/spring/java-spring-boot-bean.md)) lifecycle is how it is instantiated and destroyed
- ![](../../../attachments/Pasted%20image%2020250723091613.png)
	- take note of logs
- `@PostConstruct` -> after instantiation
- `@PreDestroy` -> before teardown
	- `"prototype"` [java-spring-boot-bean-scopes](java-spring-boot-bean-scopes.md) are NOT automatically destoryed
	- ![](../../../attachments/Pasted%20image%2020250723092835.png)
		- take note of logs; no `PreDestroy...` when scope is prototype

useful in doing custom initialization and teardown of Beans