---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-application-properties
created_at: 2025-07-25 11:28
---
```properties
spring.jpa.hibernate.ddl-auto=create
```
- tables are based on `@Entity` declaration ([java-jpa-entity-creation](dev/java/java-jpa-entity-creation.md))
- defaults to `create-drop` if using an embedded database
	- [??] the words mason, what do they mean?
- defaults to `none`
- `create-drop` creates then destroys db after
- `none` no DDL queries will be executed
- `create` option drops then creates the db
- `update` updates db schema whenever there are changes

useful in managing the database tables thru the Spring Boot application