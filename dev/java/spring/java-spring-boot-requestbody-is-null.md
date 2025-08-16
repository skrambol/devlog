--
useful in-
tags:
  - dev
  - java
  - spring-boot
  - bug
  - bug-solved
created_at: 2025-08-07 08:28
---
## Problem
```java
@PostMapping("")
public Instructor addInstructor(@RequestBody Instructor instructor) {
	System.out.println(instructor);
	return schoolService.addInstructor(instructor);
}
```
- when accessing endpoint `POST /api/instructors` with the following payload
```json
{
  "firstName": "Skrambolito",
  "lastName": "Balagbaggins",
  "email": "skrambolito@gmail.com",
  "instructorDetail": {
	"hobby": "hiking",
	"youtubeChannel": "@skrambol."
  }
}
```
![](../../../attachments/Pasted%20image%2020250807083644.png)
- all the values are `null`
	- printing the values inside the `@PostMapping`
	- as well as database logs
```log
Instructor [id=0, firstName=null, lastName=null, email=null, instructorDetail=null]
2025-08-07T08:36:11.948+08:00 DEBUG 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.SQL                        : insert into instructor (email,first_name,instructor_detail_id,last_name) values (?,?,?,?)
2025-08-07T08:36:11.948+08:00 TRACE 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (1:VARCHAR) <- [null]
2025-08-07T08:36:11.948+08:00 TRACE 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (2:VARCHAR) <- [null]
2025-08-07T08:36:11.948+08:00 TRACE 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (3:INTEGER) <- [null]
2025-08-07T08:36:11.948+08:00 TRACE 2508 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (4:VARCHAR) <- [null]
```
![](../../../attachments/Pasted%20image%2020250807083759.png)

## Solution
- due to wrong import based on this answer on stackoverflow https://stackoverflow.com/a/61354197
- make sure import is `org.springframework.web.bind.annotation.RequestBody;` instead of `io.swagger.v3.oas.annotations.parameters.RequestBody;`


useful in making sure import is correct for `@RequestBody`, `org.springframework.web.bind.annotation.RequestBody`