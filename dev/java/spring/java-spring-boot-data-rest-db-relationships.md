---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-07 08:26
---
- based here, https://www.baeldung.com/spring-data-rest-relationships, you need to POST (create) both entities then perform a PUT (update) on one of the entities to link them
- not quite good? will probably resort to using vanilla `@RestController` ([java-spring-boot-restcontroller](java-spring-boot-restcontroller.md)) together with `@Service` ([java-spring-service-annotation](java-spring-service-annotation.md))

useful in using Spring Data Rest with db relationships