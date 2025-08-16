---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter-security
created_at: 2025-08-05 16:14
aliases:
  - "JdbcUserDetailsManager"
---
```java
@Bean
public UserDetailsManager userDetailsManager(DataSource dataSource) {
// inject data source; Spring will automatically use the db as data source
	return new JdbcUserDetailsManager(dataSource);
}
```
- retrieves users for Spring Security ([java-spring-boot-starter-security](java-spring-boot-starter-security.md)) from a data source, which is usually a database
- the default `user` schema is
	- username -> varchar
	- password -> varchar
	- active -> boolean or tinyint
- the default `authorities` schema is
	- username
	- authority -> uses `ROLE_` prefix by default
- check docs for `JdbcUserDetailsManager` class https://docs.spring.io/spring-security/reference/api/java/org/springframework/security/provisioning/JdbcUserDetailsManager.html in order to customize table for users and authorities
- to use custom tables, the following should be implemented at the minimum
	- query for finding user by username -> `jdbcUserDetailsManager.setUsersByUsernameQuery("select email, password, active from members where email=?")`
	- query for finding authorities/roles by username -> `jdbcUserDetailsManager.setAuthoritiesByUsernameQuery("select email, role from roles left join members on roles.member_id = members.id where email=?")`

useful in using users already in database to be used by Spring Security