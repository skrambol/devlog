---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter
  - spring-boot-starter-parent
created_at: 2025-07-20 13:03
---
```properties
<parent>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-parent</artifactId>
	<version>3.5.3</version>
	<relativePath/> <!-- lookup parent from repository -->
</parent>
```
- Spring Boot Starters are bundled dependencies
	- results in a cleaner [maven-pom-xml](../../maven/maven-pom-xml.md) since only the starter is seen as a dependency instead of everything
	- can be picked from [java-spring-boot-project-initializer](java-spring-boot-project-initializer.md)
- uses [maven-project-metadata](../../maven/maven-project-metadata.md)
- sets the version of the other `spring-boot-starter*`

useful in bundling Spring Boot dependencies