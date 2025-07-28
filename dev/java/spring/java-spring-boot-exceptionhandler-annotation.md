---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-28 11:27
---
```java
@ExceptionHandler
public ResponseEntity<MyErrorResponse> handleException(MyException exc) {
	MyErrorResponse error = new MyErrorResponse();
	// init error values

	return new ResponseEntity<>(MyErrorResponse, HttpStatus.NOT_FOUND);
}
```
- annotation placed on method
- should have an exception as function parameters
- should return a `ResponseEntity`
	- initialized from `(Exception, HttpStatus.CODE` [java-spring-boot-httpstatus](java-spring-boot-httpstatus.md)

useful in returning custom responses whenever an exception is thrown in Spring REST