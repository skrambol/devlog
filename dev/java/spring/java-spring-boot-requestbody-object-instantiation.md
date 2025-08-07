---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-07 08:55
alias: java-spring-boot-requestbody-null-fields
---
```java
@PostMapping("")
public Instructor addInstructor(@RequestBody Instructor instructor) {
	System.out.println(instructor);
	return schoolService.addInstructor(instructor);
}
```
- `@RequestBody` ([java-spring-requestbody-annotation](dev/java/spring/java-spring-requestbody-annotation.md)) will only call `Instructor` setters if field is existing in request body payload
```json
{
  "firstName": "Skrambolito",
  "lastName": "Balagbaggins",
  // "email": "skrambolito@gmail.com", // NULL email
  "instructorDetail": {
	"hobby": "hiking",
	"youtubeChannel": "@skrambol."
  }
}
```
![](attachments/Pasted%20image%2020250807090250.png)
- for example, the payload above will not call `.setEmail()`, setting the field to null
- the logs also indicate that the email is `null`
```log
Instructor()
setFirstName
setLastName
InstructorDetail()
setHobby
setYoutubeChannel
setInstructorDetail
Instructor [id=0, firstName=Skrambolito, lastName=Balagbaggins, email=null, instructorDetail=InstructorDetail [id=0, youtube_channel=@skrambol., hobby=hiking]]
2025-08-07T08:50:44.140+08:00 DEBUG 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.SQL                        : insert into instructor_detail (hobby,youtube_channel) values (?,?)
2025-08-07T08:50:44.140+08:00 TRACE 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (1:VARCHAR) <- [hiking]
2025-08-07T08:50:44.140+08:00 TRACE 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (2:VARCHAR) <- [@skrambol.]
2025-08-07T08:50:44.143+08:00 DEBUG 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.SQL                        : insert into instructor (email,first_name,instructor_detail_id,last_name) values (?,?,?,?)
2025-08-07T08:50:44.143+08:00 TRACE 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (1:VARCHAR) <- [null]
2025-08-07T08:50:44.143+08:00 TRACE 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (2:VARCHAR) <- [Skrambolito]
2025-08-07T08:50:44.143+08:00 TRACE 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (3:INTEGER) <- [1]
2025-08-07T08:50:44.143+08:00 TRACE 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (4:VARCHAR) <- [Balagbaggins]
```
![](../../../attachments/Pasted%20image%2020250807085404.png)

useful in knowing the behavior of `@RequestBody` objects when some fields are missing from the request payload