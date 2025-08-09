---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-09 17:03
---
```java
//InstructorDetail.java
@OneToOne(mappedBy = "instructorDetail", cascade = { CascadeType.DETACH, CascadeType.MERGE, CascadeType.PERSIST, CascadeType.REFRESH })
@JsonManagedReference
private Instructor instructor;

//SchoolServiceImpl.java
@Override
@Transactional
public void deleteInstructorDetail(int id) {
	InstructorDetail instructorDetail = instructorDetailRepository.findById(id)
			.orElseThrow(() -> new RuntimeException("Instructor detail not found. ID=" + id));

	instructorDetail.getInstructor().setInstructorDetail(null);
	instructorDetailRepository.deleteById(id);
}
```
- steps: interchangeable, but both must be done
	- set `CascadeType` ([java-jpa-cascade-types](../jpa/java-jpa-cascade-types.md)) accordingly (remove `CascadeType.REMOVE`) for the `@JsonManagedReference` field from the non-owning entity
	- delete or set to null the `@JSONBackReference` from owning entity
	- call repository delete
- [??] why need both? why is calling repository delete not enough?

![](../../../attachments/Pasted%20image%2020250809164002.png)

```log
2025-08-09T16:39:33.784+08:00 DEBUG 11091 --- [schooldb] [nio-8080-exec-1] org.hibernate.SQL                        : update instructor set email=?,first_name=?,instructor_detail_id=?,last_name=? where id=?
2025-08-09T16:39:33.785+08:00 TRACE 11091 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (1:VARCHAR) <- [skrambolito.balagbaggins@email.com]
2025-08-09T16:39:33.785+08:00 TRACE 11091 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (2:VARCHAR) <- [Skrambolito]
2025-08-09T16:39:33.786+08:00 TRACE 11091 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (3:INTEGER) <- [null]
2025-08-09T16:39:33.786+08:00 TRACE 11091 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (4:VARCHAR) <- [Balagbaggins]
2025-08-09T16:39:33.786+08:00 TRACE 11091 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (5:INTEGER) <- [1]
2025-08-09T16:39:33.790+08:00 DEBUG 11091 --- [schooldb] [nio-8080-exec-1] org.hibernate.SQL                        : delete from instructor_detail where id=?
2025-08-09T16:39:33.790+08:00 TRACE 11091 --- [schooldb] [nio-8080-exec-1] org.hibernate.orm.jdbc.bind              : binding parameter (1:INTEGER) <- [1]
```
- notice that an `UPDATE` query happens first before the `DELETE`

useful in implementing 