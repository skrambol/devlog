---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter-security
created_at: 2025-08-04 13:06
---
```java
@Configuration
@EnableWebSecurity(debug = true)
public class DemoSecurityConfig {

	@Bean
	public InMemoryUserDetailsManager userDetailsManager() {
		UserDetails john = User.builder().username("john").password("{noop}test123").roles("EMPLOYEE").build();
		UserDetails susan = User.builder().username("susan").password("{noop}test123").roles("EMPLOYEE", "MANAGER", "ADMIN")
				.build();

		return new InMemoryUserDetailsManager(john, susan);
	}

```
- used together with [java-spring-boot-starter-security](dev/java/spring/java-spring-boot-starter-security.md)
- create `@Configuration` [java-spring-boot-config-bean](dev/java/spring/java-spring-boot-config-bean.md)
- create `@Bean` [java-spring-boot-bean](dev/java/spring/java-spring-boot-bean.md)
- create users with passwords and roles
	- password should follow [java-spring-boot-security-user-password-format](java-spring-boot-security-user-password-format.md)
	- roles can be any String
	- [?!] this specific snippet uses `InMemoryUserDetailsManager` however, any `UserDetailsManager` might work?
		- either `InMemoryUserDetailsManager` ([java-spring-boot-inmemoryuserdetailsmanager](java-spring-boot-inmemoryuserdetailsmanager.md)) or `JdbcUserDetailsManager` ([java-spring-boot-jdbcuserdetailsmanager](java-spring-boot-jdbcuserdetailsmanager.md)) worked

useful in creating Java Spring Security users to limit access to endpoints