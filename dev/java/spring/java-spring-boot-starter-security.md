---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter
  - spring-boot-starter-security
  - spring-boot-application-properties
created_at: 2025-07-20 13:27
---
```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-security</artifactId>
</dependency>
```
- adds username-password login for all endpoints by default
- default username is `user`
- default password can be seen in logs
	![](attachments/Pasted%20image%2020250720121147.png)
- application properties
	- `spring.security.user.name` sets a new username
	- `spring.security.user.password` sets a new password

useful in having a secure Spring Boot application that is only accessible by entering correct credentials