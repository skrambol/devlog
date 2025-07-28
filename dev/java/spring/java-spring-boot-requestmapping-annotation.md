---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-28 11:18
---
```java
import org.springframework.web.bind.annotation.RequestMapping;

@RequestMapping("/prefix")
public class MyController {

}
```
- annotation on controller class
- adds prefix URL to other endpoint mappings of the controller class

useful in adding a prefix URL for Spring REST endpoints