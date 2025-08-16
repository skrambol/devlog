---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-30 09:54
aliases:
  - "@RequestBody"
---
```java
import org.springframework.web.bind.annotation.RequestBody;


@PostMapping("")
public Employee createEmployee(@RequestBody Employee newEmployee) {
	newEmployee.setId(0);
	return employeeService.save(newEmployee);
}

```
- annotation on function parameters in spring boot endpoints ([java-spring-boot-create-endpoint](java-spring-boot-create-endpoint.md))
- the endpoint will now accept a JSON payload containing the fields of the `Employee`
- no validation seems to happen
	- no checking of fields
		- still accepted if some are missing or there are extra fields
	- no checking of values
		- numbers are seem to be converted to String if `Object.field` is a String

useful in accepting Java object as JSON payload in http request body