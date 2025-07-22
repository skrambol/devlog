---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-22 11:08
aliases:
  - 
---
```java
public class MyController {
	private MyInterface foo;
	
	@Autowired 
	public setMyInterface(MyInterface foo) {
		this.foo = foo;
	}
}
```
- Spring Boot looks for Beans ([java-spring-boot-bean](java-spring-boot-bean.md)) that have implemented the needed interface
- behind the scenes
	```java
	Coach theCoach = new CricketCoach();
	DemoController demoController = new DemoController();
	demoController.setCoach(theCoach); // <- setter injection
	```
- needs `@Autowired` in setter function
- setter function can be any function name, as long as it sets the dependency
- mostly used for optional dependencies

useful in setting dependencies via a setter function