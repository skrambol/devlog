---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-09 09:23
---
## Problem
![](../../../attachments/Pasted%20image%2020250809095252.png)
```log
2025-08-07T11:24:10.985+08:00  WARN 2508 --- [schooldb] [nio-8080-exec-5] .w.s.m.s.DefaultHandlerExceptionResolver : Ignoring exception, response committed already: org.springframework.http.converter.HttpMessageNotWritableException: Could not write JSON: Document nesting depth (1001) exceeds the maximum allowed (1000, from `StreamWriteConstraints.getMaxNestingDepth()`)
2025-08-07T11:24:10.985+08:00  WARN 2508 --- [schooldb] [nio-8080-exec-5] .w.s.m.s.DefaultHandlerExceptionResolver : Resolved [org.springframework.http.converter.HttpMessageNotWritableException: Could not write JSON: Document nesting depth (1001) exceeds the maximum allowed (1000, from `StreamWriteConstraints.getMaxNestingDepth()`)]
```
```java
//Instructor.java
@OneToOne(cascade = CascadeType.ALL)
@Nullable
@JoinColumn(name = "instructor_detail_id")
@JsonBackReference
private InstructorDetail instructorDetail;

//InstructorDetail.java
@OneToOne(mappedBy = "instructorDetail")
@JsonManagedReference
private Instructor instructor;
```
- warning when accessing GET endpoint, either for instructor or instructor detail, after adding bidirectional mapping via `@OneToOne` ([java-spring-boot-mappedby-element](../jpa/java-jpa-onetoone-annotation.md))
- most likely caused by `InstructorDetail` rendering `instructor`, then the rendered instructor also has to render `instructorDetails` and so on and so forth

## Solution
based on this stackoverflow https://stackoverflow.com/questions/45783753/spring-data-jpa-onetoone-annotation-infinite-recursion-error we can:
- introduce `@JsonIgnore` ([java-jpa-jsonignore-annotation](../jpa/java-jpa-jsonignore-annotation.md)) to either `Instructor` or `InstructorDetail`
	- ![](../../../attachments/Pasted%20image%2020250809095337.png)
	- added `@JsonIgnore` to `InstructorDetail.instructor`
- annotate `@JsonManagedRefenrence` ([java-spring-boot-jsonmanagedreference-annotation](java-spring-boot-jsonmanagedreference-annotation.md)) and `@JsonBackReference` ([java-spring-boot-jsonbackreference-annotation](java-spring-boot-jsonbackreference-annotation.md))
	- ![](../../../attachments/Pasted%20image%2020250809095411.png) 
	- code is definitely cleaner however it might be better to also show instructor detail in instructor
- make use of a Data Transfer Object (DTO)
	- [java-jpa-data-transfer-object](../jpa/java-jpa-data-transfer-object.md)
	- basically a Request/Response object that is mainly used for data transfer from server to client and vice-versa
	- https://medium.com/@roshanfarakate/understanding-dtos-in-spring-boot-a-comprehensive-guide-20e2b8101ee6
	- looks the most promising since it gives us better control on what fields to show
- used both `@JsonManagedReference`, `@JsonBackReference` to have a proper mapping and used DTO for request/response body
	
useful in solving recursive Java object to JSON rendering in response body; by using both `@JsonManagedReference` and `@JsonBackReference` annotations and implemented a Data Transfer Object (DTO)