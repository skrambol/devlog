---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-22 10:56
---
- initially Spring Boot scans the code base for `@Component` ([java-spring-boot-component-annotation](dev/java/spring/java-spring-boot-component-annotation.md)) to register it as Bean ([java-spring-boot-bean](java-spring-boot-bean.md)
- looks for classes in the same package as `@SpringBootApplication` ([java-spring-boot-springbootapplication-annotation](java-spring-boot-springbootapplication-annotation.md))
	- can be specified via [java-spring-boot-scanbasepackages](java-spring-boot-scanbasepackages.md)

useful in knowing how Spring Boot applications scan for `@Component`