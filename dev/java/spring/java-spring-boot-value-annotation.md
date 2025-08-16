---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-application-properties
created_at: 2025-07-21 11:17
aliases:
  - "@Value"
---
```properties
prop.name=this is my name
```

```java

import org.springframework.beans.factory.annotation.Value;
public class MyClass {
	@Value("${prop.name}")
	private String propName;
}
```
- annotation used to inject properties from `application.properties` ([java-spring-boot-application-properties](java-spring-boot-application-properties.md)) to code

useful in using `application.properties` in the code