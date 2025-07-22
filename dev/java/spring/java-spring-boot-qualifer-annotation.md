---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-22 11:15
aliases:
  - 
---
## Problem
[java-spring-boot-multiple-components-single-constructor-error](dev/java/spring/java-spring-boot-multiple-components-single-constructor-error.md)

## Solution
```java
import org.springframework.beans.factory.annotation.Qualifier;

@Autowired
public DemoController(@Qualifier("beanId") MyInterface myComponent) {

}
```
- specifies the `@Component` ([java-spring-boot-component-annotation](dev/java/spring/java-spring-boot-component-annotation.md)) to be used
- specify via the `"beanId"` which is just the class name but in camel case
- when both `@Qualifier` and `@Primary` ([java-spring-boot-primary-annotation](java-spring-boot-primary-annotation.md)) is present, `@Qualifer` takes priority
- much better to use since higher in priority and specificity

useful in specifying which `@Component` to use when there are multiple available