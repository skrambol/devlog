---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter
  - spring-boot-starter-actuator
  - spring-boot-application-properties
created_at: 2025-07-20 13:20
---
- adds a `/info` actuator endpoint to a Spring Boot application
- blank by default, but can be customized by the `info` application property
	```properties
	info.app.name=My App Name
	info.app.description=my app description
	info.app.version=1.0.0-SNAPSHOT
	```
- displayed as a JSON object when visiting `/actuator/info`

useful in presenting the project info in `/actuator/info` endpoint