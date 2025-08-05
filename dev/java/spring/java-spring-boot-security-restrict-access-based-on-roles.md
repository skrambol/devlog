---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter-security
created_at: 2025-08-04 20:59
---
```java
@Bean
public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
	http.authorizeHttpRequests(configurer -> configurer
			.requestMatchers(HttpMethod.GET, "/employees").hasRole("EMPLOYEE")
			.requestMatchers(HttpMethod.GET, "/employees/**").hasRole("EMPLOYEE")
			.requestMatchers(HttpMethod.POST, "/employees").hasRole("MANAGER")
			.requestMatchers(HttpMethod.PUT, "/employees").hasRole("MANAGER")
			.requestMatchers(HttpMethod.DELETE, "/employees").hasRole("ADMIN"));

	http.httpBasic(Customizer.withDefaults());

	// disabled since we are using stateless REST API; we are using Basic Auth
	http.csrf(csrf -> csrf.disable());

	return http.build();
}
```
- `requestMatchers` -> matches the HTTP method and endpoints
- `hasRole`, `hasAnyRole`, `permitAll` -> allows roles to access
- take note that `server.servlet.context-path` from application properties ([java-spring-boot-application-properties](dev/java/spring/java-spring-boot-application-properties.md)) is not part of the request URL

useful in limiting access to endpoints depending on Spring Security user roles