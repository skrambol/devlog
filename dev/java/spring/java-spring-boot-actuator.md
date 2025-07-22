---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter
  - spring-boot-starter-actuator
  - spring-boot-application-properties
created_at: 2025-07-20 13:13
---
```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```
- adds health check, info, metrics and other useful endpoints via `/actuator`

- `application.properties`
	- `management.endpoints.web.exposure.include`
		- enables endpoints for specific actuators
		- `*` -> all
		- `health,info,beans` -> allows specific actuators
		- `health` actuator is available by default
	- `management.endpoints.web.exposure.exclude`
		- disables endpoints for specific actuators
		- tried setting the value for custom endpoint but it is still protected so it seems to be only working for actuators

- sample actuators
	- `health` - health check, returns `{"status": "UP"}`
	- `info` [java-spring-boot-actuator-info](java-spring-boot-actuator-info.md)
	- `mappings` - shows all the endpoint mappings