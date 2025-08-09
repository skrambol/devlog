---
tags:
  - dev
  - java
  - spring-boot
  - java-jpa
created_at: 2025-07-24 10:48
aliases:
  - "@Entity"
---
```java
import jakarta.persistence.Entity;
import jakarta.persistence.GeneratedValue;
import jakarta.persistence.GenerationType;
import jakarta.persistence.Id;
import jakarta.persistence.Table;

@Entity
@Table(name = "student")
public class Student {

	@Id
	@GeneratedValue(strategy = GenerationType.IDENTITY)
	@Column(name = "id")
	private int id;

	@Column(name = "first_name")
	private String firstName;
```
- create Java class
- must have at least a public/protected no-argument constructor
	- [?!] but why?
		- since Spring Boot will use this to initialize the class
- add `@Entity` annotation
	- maps a Java class to a database table
	- think of Model in MVC
- add `@Table(name="")` annotation
	- by default, `@Entity` would map the table having the same class name
	- optional; but this specifies the table to be mapped
- fill in fields with `@Column(name="")` annotation
	- add `name` [java-annotation-elements](java-annotation-elements.md) for verbosity and to refactor easily later on
	- add `@Id` annotation for primary key
	- add `@GeneratedValue(strategy=GenerationType.IDENTITY)` annotation for primary key
		- `GenerationType.IDENTITY` - db identity column; used for id? auto increment?
		- `GenerationType.SEQUENCE` - db sequence
		- `GenerationType.TABLE` - ensure uniqueness in table
		- `GenerationType.UUID` - ensure global uniqueness
		- custom generation type via `org.hibernate.id.IdentifierGenerator`
			- override `public Serializable generate(...)`
- generate getters and setters via IDE code actions [nvim-lsp-code-actions-hotkey](dev/nvim/nvim-lsp-code-actions-hotkey.md)
- (optional) generate toString() via IDE code actions

useful in creating an Entity for JPA