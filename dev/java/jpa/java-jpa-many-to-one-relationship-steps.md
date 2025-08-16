---
tags:
  - dev
  - java
  - java-jpa
  - spring-boot
created_at: 2025-08-11 10:46
---
```java
//Course.java
@ManyToOne()
@JoinColumn(name = "instructor_id")
private Instructor instructor;

//Instructor.java
@OneToMany(mappedBy = "instructor")
private List<Course> courses;

public void assignCourse(Course course) {
	// handle if this.courses is still null
	this.courses.add(course);
	course.setInstructor(this);
	// remember to "save" the changes in the `@Service` layer
}
```
1. create a foreign key on the owning `@Entity` ([java-jpa-entity](java-jpa-entity.md))
	- use `@ManyToOne`([java-jpa-manytoone-annotation](java-jpa-manytoone-annotation.md)) annotation and `@JoinColumn` ([java-jpa-joincolumn-annotation](java-jpa-joincolumn-annotation.md))
2. (optional, if you want bidirectional relationship) create a field in the non-owning `@Entity`
	- use `@OneToMany` ([java-jpa-onetomany-annotation](java-jpa-onetomany-annotation.md)) annotation with the `mappedBy` ([java-jpa-mappedby-element](java-jpa-mappedby-element.md)) element
	- [??] is this really optional? maybe yes? but it is a good practice to have this
3. (needed if you do step 2) create convenience method to the non-owning `@Entity` (the one that has the `@OneToMany` field)
	- add objects to the `mappedBy` field
	- set the foreign key accordingly
	- similar to `assignCourse` method

useful in creating a bidirectional relationship between one to many and many to one in Java JPA