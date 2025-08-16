---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-09 16:11
alias:
  - java-spring-boot-dto
  - java-jpa-dto
---
- used to solve[java-spring-boot-response-recursive-rendering](../spring/java-spring-boot-response-recursive-rendering.md)
- but more than that, this might be a better practice since we would have finer control on what can be used in a request or response body
- maps `@Entity` ([java-jpa-entity](java-jpa-entity.md)) to request or response body
- not only limited to Spring Boot, can probably be used in other such as `Serializers` in `DjangoREST`
- used the following as reference on the implementation:
	- https://medium.com/@roshanfarakate/understanding-dtos-in-spring-boot-a-comprehensive-guide-20e2b8101ee6
	- https://medium.com/@mariorodrguezgalicia/what-is-a-dto-in-spring-boot-and-why-should-you-use-it-97651506e516
		- ![](../../../attachments/Pasted%20image%2020250809163158.png)
		- suggests a project structure which is quite understandable and easy to follow

- create DTO class
	```java
	public class InstructorDTO {
		private int id;
		private String firstName;
		private String lastName;
		private String email;
	
		private String youtubeChannel;
		private String hobby;
		//getters and setters
	}
	```
- create Mapper class
	```java
	@Component
	public class InstructorMapper {
		public InstructorDTO toDTO(Instructor instructor) {
			// set fields accordingly using Instructor getters and InstructorDTO setters/constructor
		}
	
		public Instructor toEntity(InstructorDTO instructorDTO) {
			// set fields accordingly using InstructorDTO getters and Instructor setters/constructor
		}
	}
	```
	- remember to annotate as `@Component` ([java-spring-boot-component-annotation](../spring/java-spring-boot-component-annotation.md)) so it can be used for dependency injection
- inject mapper as dependency of `@RestController` ([java-spring-boot-restcontroller](../spring/java-spring-boot-restcontroller.md))


useful in having another layer in limiting/controlling fields to be used as Request or Response body based on the `@Entity`