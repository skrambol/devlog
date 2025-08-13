---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-13 11:32
aliases:
  - "DataIntegrityViolationException"
---
```log
2025-08-13T10:07:38.329+08:00 DEBUG 3851 --- [schooldb] [  restartedMain] org.hibernate.SQL                        : select i1_0.id,i1_0.email,i1_0.first_name,id1_0.id,id1_0.hobby,id1_0.youtube_channel,i1_0.last_name from instructor i1_0 left join instructor_detail id1_0 on id1_0.id=i1_0.instructor_detail_id where i1_0.id=?
2025-08-13T10:07:38.329+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (1:INTEGER) <- [1]
Instructor()
InstructorDetail()
2025-08-13T10:07:38.331+08:00 DEBUG 3851 --- [schooldb] [  restartedMain] org.hibernate.SQL                        : delete from instructor where id=?
2025-08-13T10:07:38.332+08:00 TRACE 3851 --- [schooldb] [  restartedMain] org.hibernate.orm.jdbc.bind              : binding parameter (1:INTEGER) <- [1]
2025-08-13T10:07:38.337+08:00  WARN 3851 --- [schooldb] [  restartedMain] o.h.engine.jdbc.spi.SqlExceptionHelper   : SQL Error: 0, SQLState: 23503
2025-08-13T10:07:38.338+08:00 ERROR 3851 --- [schooldb] [  restartedMain] o.h.engine.jdbc.spi.SqlExceptionHelper   : ERROR: update or delete on table "instructor" violates foreign key constraint "fk79arv901b5gkyp2240wcm3l76" on table "courses"
  Detail: Key (id)=(1) is still referenced from table "courses".
2025-08-13T10:07:38.345+08:00  INFO 3851 --- [schooldb] [  restartedMain] .s.b.a.l.ConditionEvaluationReportLogger :

Error starting ApplicationContext. To display the condition evaluation report re-run your application with 'debug' enabled.
2025-08-13T10:07:38.357+08:00 ERROR 3851 --- [schooldb] [  restartedMain] o.s.boot.SpringApplication               : Application run failed

org.springframework.dao.DataIntegrityViolationException: could not execute statement [ERROR: update or delete on table "instructor" violates foreign key constraint "fk79arv901b5gkyp2240wcm3l76" on table "courses"
  Detail: Key (id)=(1) is still referenced from table "courses".] [delete from instructor where id=?]; SQL [delete from instructor where id=?]; constraint [fk79arv901b5gkyp2240wcm3l76]
```
![](../attachments/Pasted%20image%2020250813101005.png)
- not removing associations will raise `DataIntegrityViolationException` which means that the foreign key should have an existing reference if not null
- udemy lesson actually raised `SQLIntegrityConstraintViolationException` but same concept

useful in remembering to also remove associated fields to avoid this error in Spring Boot