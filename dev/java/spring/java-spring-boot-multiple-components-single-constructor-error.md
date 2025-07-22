---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-07-21 10:38
aliases:
---
- due to the introduction of [java-spring-boot-spring-containers](java-spring-boot-spring-containers.md), how will Spring Boot handle/choose if there are multiple components implementing the dependency or the needed interface by the controller
- it turns out, it is an error `org.springframework.beans.factory.UnsatisfiedDependencyException: Error creating bean with name 'funRestController' defined in file [/home/skrambol/java-man/mycoolerapp/target/classes/com/skrambolito/springboot/demo/mycoolerapp/rest/FunRestController.class]: Unsatisfied dependency expressed through constructor parameter 0: No qualifying bean of type 'com.skrambolito.springboot.demo.mycoolerapp.rest.Coach' available: expected single matching bean but found 3: cricketCoach,esportsCoach,lifeCoach`

```log
2025-07-21T10:34:47.699+08:00  INFO 8812 --- [mycoolerapp] [  restartedMain] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 1124 ms
2025-07-21T10:34:47.869+08:00  WARN 8812 --- [mycoolerapp] [  restartedMain] ConfigServletWebServerApplicationContext : Exception encountered during context initialization - cancelling refresh attempt: org.springframework.beans.factory.UnsatisfiedDependencyException: Error creating bean with name 'funRestController' defined in file [/home/skrambol/java-man/mycoolerapp/target/classes/com/skrambolito/springboot/demo/mycoolerapp/rest/FunRestController.class]: Unsatisfied dependency expressed through constructor parameter 0: No qualifying bean of type 'com.skrambolito.springboot.demo.mycoolerapp.rest.Coach' available: expected single matching bean but found 3: cricketCoach,esportsCoach,lifeCoach
2025-07-21T10:34:47.871+08:00  INFO 8812 --- [mycoolerapp] [  restartedMain] o.apache.catalina.core.StandardService   : Stopping service [Tomcat]
2025-07-21T10:34:47.891+08:00  INFO 8812 --- [mycoolerapp] [  restartedMain] .s.b.a.l.ConditionEvaluationReportLogger :

Error starting ApplicationContext. To display the condition evaluation report re-run your application with 'debug' enabled.
2025-07-21T10:34:47.908+08:00 ERROR 8812 --- [mycoolerapp] [  restartedMain] o.s.b.d.LoggingFailureAnalysisReporter   :

***************************
APPLICATION FAILED TO START
***************************

Description:

Parameter 0 of constructor in com.skrambolito.springboot.demo.mycoolerapp.rest.FunRestController required a single bean, but 3 were found:
        - cricketCoach: defined in file [/home/skrambol/java-man/mycoolerapp/target/classes/com/skrambolito/springboot/demo/mycoolerapp/rest/CricketCoach.class]
        - esportsCoach: defined in file [/home/skrambol/java-man/mycoolerapp/target/classes/com/skrambolito/springboot/demo/mycoolerapp/rest/EsportsCoach.class]
        - lifeCoach: defined in file [/home/skrambol/java-man/mycoolerapp/target/classes/com/skrambolito/springboot/demo/mycoolerapp/rest/LifeCoach.class]

This may be due to missing parameter name information

Action:

Consider marking one of the beans as @Primary, updating the consumer to accept multiple beans, or using @Qualifier to identify the bean that should be consumed

Ensure that your compiler is configured to use the '-parameters' flag.
You may need to update both your build tool settings as well as your IDE.
(See https://github.com/spring-projects/spring-framework/wiki/Spring-Framework-6.1-Release-Notes#parameter-name-retention)
```
	
useful in understanding that it is not allowed to have multiple components and only one constructor for Spring Boot dependency injection