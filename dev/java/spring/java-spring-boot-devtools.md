---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-devtools
created_at: 2025-07-20 12:44
---
## Problem
surely there is a hot reload option for Spring Boot

## Solution
```xml
<!-- spring booty dev tools for the funs ng bayan -->
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-devtools</artifactId>
	<optional>true</optional>
</dependency>
```
- mahmen Kidd suggested to use this instead of manually watching files
- based on [official docs](https://docs.spring.io/spring-boot/reference/using/devtools.html)

useful in hot reloading Spring Boot applications via dev