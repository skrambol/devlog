---
tags:
  - dev
  - java
  - spring-boot
  - spring-boot-starter-security
created_at: 2025-08-04 21:16
---
## Problem
- encountered an error while following udemy lesson about [java-spring-boot-security-restrict-access-based-on-roles](java-spring-boot-security-restrict-access-based-on-roles.md)
- 403 forbidden being thrown even if request matchers are the same
- even tried `.permitAll()` (shoutout Gio) on request matcher and yet it is still not working
- remembered that the setup for endpoints on my code is using context-path while udemy lesson does not

## Solution
- only filter endpoints as declared on `@RestController`, no need to include context-path
- searched for "spring boot http request matchers and servlet.context-path"
- https://stackoverflow.com/questions/70481700/spring-security-ignoring-context-path
- `@EnableWebSecurity(debug=true)` to Security `@Configuration` to enable logging
- it turns out that `server.servlet.context-path` ([java-spring-boot-application-properties](dev/java/spring/java-spring-boot-application-properties.md)) is not included when filtering
- when using context path, it logs `Request received from GET '/employees'`, context-path not really part of the request
	```
	2025-08-04T11:41:44.801+08:00  INFO 13548 --- [nio-8080-exec-1] Spring Security Debugger                 :
	
	************************************************************
	
	Request received for GET '/employees':
	
	org.apache.catalina.connector.RequestFacade@54aad0af
	
	servletPath:/employees
	pathInfo:null
	headers:
	accept: application/json, text/plain, */*
	user-agent: bruno-runtime/2.8.1
	authorization: Basic am9objp0ZXN0MTIz
	cookie: JSESSIONID=EDC2E76AD52FA265B70725F296F867F0
	request-start-time: 1754278904794
	accept-encoding: gzip, compress, deflate, br
	host: localhost:8080
	connection: keep-alive
	
	
	Security filter chain: [
	  DisableEncodeUrlFilter
	  WebAsyncManagerIntegrationFilter
	  SecurityContextHolderFilter
	  HeaderWriterFilter
	  LogoutFilter
	  BasicAuthenticationFilter
	  RequestCacheAwareFilter
	  SecurityContextHolderAwareRequestFilter
	  AnonymousAuthenticationFilter
	  ExceptionTranslationFilter
	  AuthorizationFilter
	]
	
	
	************************************************************
	
	```
- comparing it to not setting `context-path`, `servletPath` is similar to full endpoint
	```
		2025-08-04T11:37:02.996+08:00  INFO 13213 --- [nio-8080-exec-1] Spring Security Debugger                 :
		
		************************************************************
		
		Request received for GET '/api/employees':
		
		org.apache.catalina.connector.RequestFacade@44b2c57f
		
		servletPath:/api/employees
		pathInfo:null
		headers:
		accept: application/json, text/plain, */*
		user-agent: bruno-runtime/2.8.1
		authorization: Basic am9objp0ZXN0MTIz
		cookie: JSESSIONID=EDC2E76AD52FA265B70725F296F867F0
		request-start-time: 1754278622900
		accept-encoding: gzip, compress, deflate, br
		host: localhost:8080
		connection: keep-alive
		
		
		Security filter chain: [
		DisableEncodeUrlFilter
		WebAsyncManagerIntegrationFilter
		SecurityContextHolderFilter
		HeaderWriterFilter
		LogoutFilter
		BasicAuthenticationFilter
		RequestCacheAwareFilter
		SecurityContextHolderAwareRequestFilter
		AnonymousAuthenticationFilter
		ExceptionTranslationFilter
		AuthorizationFilter
		]
		
		
		************************************************************
	```

useful in knowing that `requestMatch` only filter endpoints as declared on `@RestController`, no need to include `server.servlet.context-path`