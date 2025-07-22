---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-22 10:49
  - 
---
```java
public class MyController {
	private MyInterface foo;
	
	@Autowired //optional
	public MyController(MyInterface foo) {
		this.foo = foo;
	}
}
```
- Spring Boot looks for available Bean ([java-spring-boot-bean](java-spring-boot-bean.md)) that have implemented `MyInterface`
- behind the scenes
	```java
	Coach theCoach = new CricketCoach();
	DemoController demoController = new DemoController(theCoach); // <- constructor injection
	```
- mostly used for required dependencies
- recommended by Spring team to use primarily

useful in injecting dependencies to the controller via the constructor