---
tags:
  - dev
  - java
  - spring
  - spring-boot
created_at: 2025-07-18 07:14
aliases:
---
## Problem
tutorial clicks Run on IDE to run Spring Boot application. but i dont have it

## Solution
- to use command line instead
- tried running `./mvnw spring-boot:run` on same directory, no output but cancelling shows failed wget
- it turns out script is downloading slowly
- based on [official docs](https://spring.io/guides/gs/spring-boot)

useful in running Spring Boot applications on the command line