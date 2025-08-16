---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-07 09:40
---
```java
@Entity
@Table(name = "instructor")
public class Instructor {
	@Id
	@GeneratedValue(strategy = GenerationType.IDENTITY)
	@JsonIgnore
	@Column(name = "id")
	private int id;

	@NotNull
	@NotBlank
	@Column(name = "first_name")
	private String firstName;

	@NotNull
	@Column(name = "last_name")
	private String lastName;

	@Column(name = "email")
	private String email;

	@OneToOne(cascade = CascadeType.ALL)
	@Nullable
	@JoinColumn(name = "instructor_detail_id")
	private InstructorDetail instructorDetail;
	//getters and setters
}
```

```java
@Entity
@Table(name = "instructor_detail")
public class InstructorDetail {
	@Id
	@GeneratedValue(strategy = GenerationType.IDENTITY)
	@JsonIgnore
	@Column(name = "id")
	private int id;

	@Column(name = "youtube_channel")
	private String youtubeChannel;

	@Column(name = "hobby")
	private String hobby;
	//getters and setters
}
```

```java
@PostMapping("")
public Instructor addInstructor(@RequestBody Instructor instructor) {
	System.out.println(instructor);
	return schoolService.addInstructor(instructor);
}
```
- when `@Entity` ([java-jpa-entity](../jpa/java-jpa-entity.md)) with a `@OneToOne` ([java-jpa-onetoone-annotation](../jpa/java-jpa-onetoone-annotation.md)) mapping is used as `@RequestBody` ([java-spring-requestbody-annotation](java-spring-requestbody-annotation.md)) payload should be nested as another object
```json
{
	"firstName": "first",
	"lastName": "last",
	"email": "email",
	"instructorDetail": {
		"youtubeChannel": "channel21",
		"hobby": "typing"
	}
}
```
![](../../../attachments/Pasted%20image%2020250807095107.png)

useful in using an `@Entity` with `@OneToOne` field mapping as a `@RequestBody` payload