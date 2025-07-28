---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-28 11:34
---
```java
import org.springframework.http.HttpStatus;
HttpStatus.OK;
HttpStatus.NOT_FOUND;
```
- `HttpStatus.OK`
- `HttpStatus.NOT_FOUND`
- take note that these are enumerations, to use `int` value, call `.value()`

useful in using HTTP status codes in Spring Application