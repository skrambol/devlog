---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-13 11:29
---
```java
@Override
@Transactional
public void deleteInstructor(int id) {
	Instructor instructor = getInstructor(id);

	for (Course c : instructor.getCourses()) {
		c.setInstructor(null); // remove association
	}

	instructorRepository.deleteById(id); //delete
}
```
```log
2025-08-13T10:04:05.500+08:00 DEBUG 3851 --- [schooldb] [  restartedMain] org.hibernate.SQL                        : select i1_0.id,i1_0.email,i1_0.first_name,id1_0.id,id1_0.hobby,id1_0.youtube_channel,i1_0.last_name from instructor i1_0 left join instructor_detail id1_0 on id1_0.id=i1_0.instructor_detail_id where i1_0.id=?
2025-08-13T10:04:05.500+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (1:INTEGER) <- [1]
Instructor()
InstructorDetail()
skrambolito.balagbaggins@email.com.getCourses()
2025-08-13T10:04:05.504+08:00 DEBUG 3851 --- [schooldb] [  restartedMain] org.hibernate.SQL                        : select c1_0.instructor_id,c1_0.id,c1_0.title from courses c1_0 where c1_0.instructor_id=?
2025-08-13T10:04:05.504+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (1:INTEGER) <- [1]
Course()
Course()
Course()
2025-08-13T10:04:05.511+08:00 DEBUG 3851 --- [schooldb] [  restartedMain] org.hibernate.SQL                        : update courses set instructor_id=?,title=? where id=?
2025-08-13T10:04:05.511+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (1:INTEGER) <- [null]
2025-08-13T10:04:05.511+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (2:VARCHAR) <- [A01]
2025-08-13T10:04:05.511+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (3:INTEGER) <- [1]
2025-08-13T10:04:05.512+08:00 DEBUG 3851 --- [schooldb] [  restartedMain] org.hibernate.SQL                        : update courses set instructor_id=?,title=? where id=?
2025-08-13T10:04:05.512+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (1:INTEGER) <- [null]
2025-08-13T10:04:05.512+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (2:VARCHAR) <- [A02]
2025-08-13T10:04:05.513+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (3:INTEGER) <- [2]
2025-08-13T10:04:05.514+08:00 DEBUG 3851 --- [schooldb] [  restartedMain] org.hibernate.SQL                        : update courses set instructor_id=?,title=? where id=?
2025-08-13T10:04:05.514+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (1:INTEGER) <- [null]
2025-08-13T10:04:05.514+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (2:VARCHAR) <- [A03]
2025-08-13T10:04:05.514+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (3:INTEGER) <- [3]
2025-08-13T10:04:05.516+08:00 DEBUG 3851 --- [schooldb] [  restartedMain] org.hibernate.SQL                        : delete from instructor where id=?
2025-08-13T10:04:05.516+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (1:INTEGER) <- [1]
2025-08-13T10:04:05.518+08:00 DEBUG 3851 --- [schooldb] [  restartedMain] org.hibernate.SQL                        : delete from instructor_detail where id=?
2025-08-13T10:04:05.518+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (1:INTEGER) <- [1]
```
![](../../../attachments/Pasted%20image%2020250813100752.png)
- deleting an `@Entity` ([java-jpa-entity](java-jpa-entity.md)) with `@OneToMany` field
- always remember to remove association (set `@ManyToOne` or foreign key field of owning entity to none)
- unlike `@ManyToOne` delete, you can just proceed with delete
- notice the logs show performing delete then updating related entities
- inverse of [java-jpa-many-to-one-relationship-steps](java-jpa-many-to-one-relationship-steps.md)

useful to remember removing associations before deleting an `@Entity` with `@OneToMany` field/attribute in Spring Boot