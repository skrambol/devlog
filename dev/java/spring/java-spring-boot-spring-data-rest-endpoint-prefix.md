---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-application-properties
created_at: 2025-07-31 10:57
alias: java-spring-boot-data-rest-url-prefix
---
```properties
spring.data.rest.base-path=/magic
```
- url prefix for Spring Data REST [java-spring-boot-data-rest](java-spring-boot-data-rest.md)
- placed after `server.servlet.context-path` if exists
- check docs ([java-spring-boot-application-properties-docs](java-spring-boot-application-properties-docs.md)) for `spring.data.rest.*` for more in properties

useful in customizing the prefix for Spring Data REST endpoints