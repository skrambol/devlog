---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-22 11:25
  - 
---
```
import org.springframework.context.annotation.Lazy;

@Lazy
@RestController
public class MyClass {

}
```
- only initialize a Bean ([java-spring-boot-bean](java-spring-boot-bean.md)) when first called
- can be used for `@RestController` ([java-spring-boot-restcontroller](dev/java/spring/java-spring-boot-restcontroller.md)) and `@Component` ([java-spring-boot-component-annotation](dev/java/spring/java-spring-boot-component-annotation.md))

useful in lazy loading a specific Bean