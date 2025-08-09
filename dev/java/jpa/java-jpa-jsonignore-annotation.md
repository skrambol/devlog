---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-07 09:53
aliases:
  - "@JsonIgnore"
---
## Problem
- by default, the `id` is being added to the response body
- it is better to remove it to obfuscate some sensitive details

## Solution
```java
@Entity
@Table(name = "instructor")
public class Instructor {
	@Id
	@GeneratedValue(strategy = GenerationType.IDENTITY)
	@JsonIgnore
	@Column(name = "id")
	private int id;
}
```
- first solution was to create custom response class but has no id
- even better solution: searched `spring boot rest remove id from api response` in google
- learned about `@JsonIgnore` from AI recap :(
- added as annotation to `@Entity` ([java-jpa-entity](java-jpa-entity.md)) fields

useful in excluding fields (not only `id`) from response body