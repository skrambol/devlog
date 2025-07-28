---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-28 11:36
---
```java
@ControllerAdvice
public class RestExceptionHandler {
	@ExceptionHandler
	public ResponseEntity<MyErrorResponse> handleException(MyException exc) { }
}
```
- annotation on class
- pre-process of request
- post-process of response
- somewhat acts as a middleware
- can be used as a global exception handler by having a `@ExceptionHandler` ([java-spring-boot-exceptionhandler-annotation](java-spring-boot-exceptionhandler-annotation.md)) method

useful in pre-process of request, post-process of response such as exception handling