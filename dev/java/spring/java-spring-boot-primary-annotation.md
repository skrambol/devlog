---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-22 11:18
aliases:
  - "@Primary"
---
## Problem
[java-spring-boot-multiple-components-single-constructor-error](java-spring-boot-multiple-components-single-constructor-error.md)

## Solution
```java
import org.springframework.beans.factory.annotation.Primary;

@Primary
@Component
public class MyComponent implements MyInterface { }
```
- sets the `@Component` ([java-spring-boot-component-annotation](java-spring-boot-component-annotation.md)) as primary, which means this should be used
- will throw an error if there are multiple `@Primary` components

useful in setting a *primary* `@Component` when there are multiple available