---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-23 11:00
---
```java
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class Config {
	@Bean("customId")
	public Interface defaultId() {
		return new SomeClass();
	}
}


```
- allows an existing (third party) class to be a Spring Bean ([java-spring-boot-bean](java-spring-boot-bean.md))
- `@Configuration`
	- base class for Bean configs
- `@Bean`
	- annotates the function(?) to be a Spring Bean
	- by default, the function name would be the Bean ID
	- can be further customized by passing an argument in the annotation

useful in exposing already existing (mostly third party) classes to be discovered as a Spring Bean