---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-12 13:47
---
```java
// Courses.java
@ManyToOne(etch = FetchType.LAZY)
@JoinColumn(name = "instructor_id")
private Instructor instructor;

// CourseRepository.java
public interface CourseRepository extends JpaRepository<Course, Integer> {

	List<Course> findByInstructor(Instructor instructor);
}

// SchoolServiceImpl.java
@Override
public List<Course> getAllCoursesOfInstructor(int instructorId) {
	Instructor instructor = new Instructor();
	instructor.setId(instructorId); 

	return courseRepository.findByInstructor(instructor);
}

```
- `JpaRepository` ([java-spring-jparepository](java-spring-jparepository.md)) allows for a way to "automatically" find an `@Entity` ([java-jpa-entity](../jpa/java-jpa-entity.md)) depending on its fields
- method `findBy{Column}` where `{Column}` is a `@Column`  field
	- autocomplete also adds the appropriate return type. `List<@Entity>` if it has many to one relationship to `@Column`

![](../../../attachments/Pasted%20image%2020250812101400.png)
```log
2025-08-12T10:13:11.604+08:00  INFO 4250 --- [schooldb] [nio-8080-exec-1] o.a.c.c.C.[Tomcat].[localhost].[/api]    : Initializing Spring DispatcherServlet 'dispatcherServlet'
2025-08-12T10:13:11.605+08:00  INFO 4250 --- [schooldb] [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Initializing Servlet 'dispatcherServlet'
2025-08-12T10:13:11.606+08:00  INFO 4250 --- [schooldb] [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Completed initialization in 1 ms
Instructor()
setId
2025-08-12T10:13:11.733+08:00 DEBUG 4250 --- [schooldb] [nio-8080-exec-1] org.hibernate.SQL                        : select c1_0.id,c1_0.instructor_id,c1_0.title from courses c1_0 where c1_0.instructor_id=?
2025-08-12T10:13:11.734+08:00 TRACE 4250 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (1:INTEGER) <- [1]
Instructor()
```
- checked logs and it only seems that the ID is the one only being used in the query
	- this means that maybe no need to pass the exact same instance/object for the `findByColumn` as long as the id or pimary key are the same (mappedBy?)

useful in getting 