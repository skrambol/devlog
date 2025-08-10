---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-28 11:22
aliases:
  - "@PathVariable"
---
```java
@GetMapping("/hello/{id}")
public getHello(@PathVariable int id) {
	return EntityDAO.getById(id);
}
```
- annotation placed on function parameters
- dynamically passes data/value from URL

useful in dynamically passing data/value from URL