---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-application-properties
created_at: 2025-07-20 12:58
aliases:
  - "application properties"
---
```properties
spring.application.name=mycoolerapp
server.port=42069

management.endpoints.web.exposure.include=*
management.info.env.enabled=true

management.endpoints.web.exposure.exclude=endpoint-ng-bayan

info.app.name=My App Name
info.app.description=my app description
info.app.version=1.0.0-SNAPSHOT
```
- located in `src/main/resources/application.properties` in a [maven-standard-java-project-directory](../../maven/maven-standard-java-project-directory.md)

useful in setting up project variables for a Spring Boot application