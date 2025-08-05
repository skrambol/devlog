---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter-security
  - bruno
created_at: 2025-08-04 20:50
---
- Spring Security REST endpoints uses `Basic Auth` from request header
- ![](../../../attachments/Pasted%20image%2020250804092750.png)
	- experiencing http status 999 when accessing endpoints using Bruno even if entering correct user credentials
	- it turns out, credentials should be passed as part of `Basic Auth` Authentication request header

useful in understanding that the default Authorization header for Spring Security is `Basic Auth`