---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter-security
created_at: 2025-08-04 13:14
---
```java
UserDetails susan = User.builder().username("susan").password("{noop}test123").roles("EMPLOYEE", "MANAGER", "ADMIN")
```
- [java-spring-boot-starter-security](dev/java/spring/java-spring-boot-starter-security.md) follows the following format for password `{encryption}password`
- example of encryption
	- `noop` -> no encryption, only plaintext
	- `bcrypt` -> uses bcrypt encryption

useful in declaring a password for Java Spring Security user by following the specified format