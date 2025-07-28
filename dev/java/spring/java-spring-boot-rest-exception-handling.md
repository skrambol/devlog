---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-28 11:25
---
## Steps
1. create custom response class that has information about the error
	- status code
	- message
	- trace? timestamp?
2. create custom exception class
	- `extends Exception`
	- `super(message)`
3. throw custom exception in `@RestController` ([java-spring-boot-restcontroller](dev/java/spring/java-spring-boot-restcontroller.md))
4. create `@ExceptionHandler` method [java-spring-boot-exceptionhandler-annotation](java-spring-boot-exceptionhandler-annotation.md)

useful in creating custom error responses for Spring REST