---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter-security
created_at: 2025-08-05 16:12
aliases:
  - "InMemoryUserDetailsManager"
---
```java
@Bean
public InMemoryUserDetailsManager userDetailsManager() {
	UserDetails john = User.builder().username("john").password("{noop}test123").roles("EMPLOYEE").build();
	UserDetails susan = User.builder().username("susan").password("{noop}test123").roles("EMPLOYEE", "MANAGER", "ADMIN")
			.build();

	return new InMemoryUserDetailsManager(john, susan);
}
```
- creates users for Spring Security ([java-spring-boot-starter-security](java-spring-boot-starter-security.md)) in memory only

useful in creating users in the memory for Spring Security