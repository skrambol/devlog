---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-20 12:38
---
```java
	@GetMapping("/endpoint-ng-bayan")
	public String sayHello() {
		return "hello bayan";
	}
```
- "maps" endpoint to an HTTP verb
- different annotations used to creating endpoints
	- `@GetMapping`
	- `@PostMapping`
	- `@PutMapping`
	- `@PatchMapping`
	- `@DeleteMapping`
- pass the specific endpoint as annotation arguments

useful in creating a new endpoint under a [java-spring-boot-restcontroller](java-spring-boot-restcontroller.md)