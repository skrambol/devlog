---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter-security
created_at: 2025-08-05 17:06
---
## Problem
```log
2025-08-05T09:43:30.605+08:00  WARN 3983 --- [  restartedMain] r$InitializeUserDetailsManagerConfigurer : Found 2 UserDetailsService beans, with names [userDetailsManager, inMemoryUserDetailsManager]. Global Authentication Manager will not use a UserDetailsService for username/password login. Consider publishing a single UserDetailsService bean.
```
- using the `JdbcUserDetailsManager` ([java-spring-boot-jdbcuserdetailsmanager](java-spring-boot-jdbcuserdetailsmanager.md)) and `InMemoryUserDetailsManager` ([java-spring-boot-inmemoryuserdetailsmanager](java-spring-boot-inmemoryuserdetailsmanager.md)) at the same time results in a warning
- using credentials from any `UserDetailsManager` results in `401 Unauthorized`
- even using the one set in application properties ([java-spring-boot-starter-security](java-spring-boot-starter-security.md))

## Solution
- only have one `UserDetailsManager` Bean ([java-spring-boot-bean](java-spring-boot-bean.md)) in your Spring Boot Application

useful in knowing the limit of having only one `UserDetailsManager` for your Spring Booot Application