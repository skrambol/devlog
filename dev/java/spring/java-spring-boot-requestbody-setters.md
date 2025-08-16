---
tags:
  - dev
  - java
  - spring-boot
created_at: 2025-08-07 09:13
---
## Problem
- encountered an exception (`NullPointerException`?) when calling an endpoint
- endpoint was not processed at all since the issue is most likely from the `@RequestBody` ([java-spring-requestbody-annotation](java-spring-requestbody-annotation.md))
- encountered this error which prompted me to investigate the instantiation ([java-spring-boot-requestbody-object-instantiation](java-spring-boot-requestbody-object-instantiation.md))
- my `setFirstName` implementation also updates email (`{firstInitial}.{lastName.trim().toLowerCase()}@email.com`)
	- but since currently, `lastName` is still null, this raised an error

## Solution
- as much as possible, keep setters to only set their values
- carefully think about the implementation to avoid this error

useful in being mindful when implementing setters especially when updating more than one value since other values might still be null