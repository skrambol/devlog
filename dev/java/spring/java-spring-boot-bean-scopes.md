---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-22 11:31
---
```java
import org.springframework.context.annotation.Scope;

@Component
@Scope("prototype")
public class MyComponent implements MyInterface {}
```
![](../../../attachments/Pasted%20image%2020250722104402.png)
- by default, Beans ([java-spring-boot-bean](java-spring-boot-bean.md)) are created as singletons
- singleton -> only one instance created
- `prototype` -> creates an instance each time being injected
- [??] might be useful when the Bean needs to be an instance of a User or Profile

useful in specifying the scope of the Bean