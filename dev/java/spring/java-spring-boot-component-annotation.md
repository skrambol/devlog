---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-21 11:29
aliases:
---
```java
import org.springframework.stereotype.Component;

@Component
public class MyComponent implements MyInterface {

}
```
- `@Component` annotates the class to be a Spring Bean to be handled by Spring
- marks the class to be usable for dependency injection by the [java-spring-boot-spring-containers](java-spring-boot-spring-containers.md)

useful in creating dependencies for controllers in Spring Boot applications