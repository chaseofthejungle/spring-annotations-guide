# Spring Annotations Guide
  
#### Table of Contents:
  
1. [Spring Aspect-Oriented Programming (AOP)](#spring-aop)
2. [Spring Boot](#spring-boot)
3. [Spring Cloud](#spring-cloud)
4. [Spring Core](#spring-core)
5. [Spring Data](#spring-data)
6. [Spring MVC](#spring-mvc)
7. [Spring Scheduling](#spring-scheduling)
8. [Spring Security](#spring-security)
9. [Spring Testing](#spring-testing)
10. [Supplemental Resources](#supplemental)
  
<hr />

## 1. <a name="spring-aop">Spring Aspect-Oriented Programming (AOP)</a>
  
| Concept | Explanation |
| -------- | -------- |
| `Aspects` | Aspects are classes that implement enterprise app behavior, cutting across more than one class in doing so. There are multiple ways to configure an aspect, such as through XML or using the AspectJ integration. |
| `Join Points` | Join points are points/places in apps in which tasks are performed, such as modifying variable values of objects, handling exceptions, and running methods. Join points are 'located' at the execution points of methods. |
| `Pointcuts` | Pointcut expressions (using AspectJ pointcut expression language) are associated with join points, and evaluate if an advice is to be executed. |
| `Advices` | Advices are actions that are performed for their associated join points. These methods are ran when join points with associated pointcuts are reached in app execution. |
| `Target Objects` | Advices are associated with these proxied objects. These use runtime proxies, which means that subclasses are established at runtime (configurations determine which advices are to be applied and target methods are overridden). |
| `Proxies` | Proxy classes are established (via JDK dynamic proxy), which are associated with advice markings/invocations and target classes (AOP proxy classes). |
| `Weaving` | The tasks that associates aspects with related objects, establishing the advised proxy objects. AOP natively does this at. |
<br />  

**Essential Annotations include:**
| Annotation | Explanation |
| -------- | -------- |
| `@Aspect` | Marks/indicates that a class is an aspect, and can cut across more than one class (such as for enterprise app implementations). |
| `@Pointcut` | Declares reusable pointcut expressions. |
| `@Before` | Indicates that an advice is to run before a method is executed. |
| `@After` | Indicates that an advice is to run after a method is executed (regardless of which it terminates properly or by throwing an exception). |
| `@Around` | Indicates that an advice wraps around, or surrounds, a method. Invokes a specified join point method. |
| `@AfterThrowing` | Indicates that an advice is to run after a method executes and throws an exception (method does not run properly/normally). |
| `@AfterReturning` | Indicates that an advice is to run after a method executes and returns properly (without throwing an exception). |

<hr />  

## 2. <a name="spring-boot">Spring Boot</a>
  
**Overview:** Spring Boot is an open source framework of libraries for the setup, programming, configuration, and deployment of Java microservice applications. Examples of Spring Boot features include diagnostic checks, production-ready metrics, customizable startup configurations, and embedded app servers (e.g., Jetty, Tomcat, Undertow). No code or XML generation is necessary to create Spring Boot projects, and best configurations for projects are automatically determined (and manually adjustable, as desired or needed).
  
**Essential Annotations include:**
| Annotation | Explanation |
| -------- | -------- |
| @SpringBootApplication | Configures/bootstraps Spring apps by combining @ComponentScan, @Configuration, and @EnableAutoConfiguration. |
| @EnableAutoConfiguration | Configures Spring app with common components, without the need for manual registration of beans. |
| @EnableConfigurationProperties | Used when binding external configurations to Plain Old Java Objects (POJOs). |
| @RestController | Establishes RESTful services by combining @ResponseBody and @Controller. |
| @Values | Injects properties from environment variables and configuration setups. |
| @ConditionalOnMissingBean | Configures beans if not previously defined. |
| @ConditionalOnProperty | Configures beans if environmental property is present. |
  
<hr />

## 3. <a name="spring-cloud">Spring Cloud</a>
  
**Overview:** Spring Cloud enables distributed systems developers to easily set up Cloud services and apps (through annotations and adopting/adapting boilerplate code), including managing various components and functionalities of Cloud-based systems (e.g., dynamic routing configurations, microservice proxy systems, control bus communications, circuit breaking, Spring Cloud contract tests, service discovery systems).
<br />
  
**Essential Annotations include:**
| Annotation | Explanation |
| -------- | -------- |
| `@EnableDiscoveryClient` | Toggles on the service discovery client for Spring Cloud web apps. |
| `@FeignClient` | Indicates a declarative Feign service client (used for web-based microservice communications). |
| `@EnableCircuitBreaker` | Provides abstraction layer for circuit breaking technologies. |
| `@HystrixCommand` | Used for determining when to open/close circuits, and provides fault tolerance. |
| `@RefreshScope` | Provides dynamic, runtime-based refreshing of bean definitions/configuration properties. |
<hr />

## 4. <a name="spring-core">Spring Core</a>
(TODO)
<hr />
  
## 5. <a name="spring-data">Spring Data</a>
(TODO)  
<hr />
  
## 6. <a name="spring-mvc">Spring MVC</a>
(TODO)
<hr />
  
## 7. <a name="spring-scheduling">Spring Scheduling</a>
  
**Overview:** Process automation, performance, and various app functionalities can be enhanced through Spring's task/process scheduling mechanism (the TaskScheduler interface).
<br />

**Essential Annotations include:**
| Annotation | Explanation |
| -------- | -------- |
| `@Scheduled` | Schedules processes to run routinely or as otherwise specified. |
| `@Schedules` | Indicates multiple scheduling rules for the app. |
| `@EnableScheduling` | Toggles on scheduling support for the app. |
| `@Async` | Indicates that a method is to be ran asynchronously. |
| `@EnableAsync` | Toggles on asynchronous processing for the app. | 
<hr />

## 8. <a name="spring-security">Spring Security</a>
  
**Overview:** The Spring Security framework includes mechanisms for authentication (such as single sign-on capabilities) and authorization, as well as securing apps against popular web security attacks. 
<br />
  
**Essential Annotations include:** 
| Annotation | Explanation |
| -------- | -------- |
| `@EnableWebSecurity` | Toggles Spring Security to on for the associated app. |
| `@PreFilter` | Provides an expression that, if true, adds a class or method to a security filter chain. |
| `@PostFilter` | Provides an expression that, if determined to be true after a class or method is ran, adds it to a security filter chain. |
| `@Secured` | Defines role-associated security for methods. |
| `@RolesAllowed` | Indicates which roles can access a method. |
| `@PreAuthorize` | Indicates pre-authorization checks for methods. |
| `@PostAuthorize` | Indicates post-authorization checks for methods. |
| `@RoleHierarchy` | States permitted roles, clarifying security configuration (and limiting the need for @PreAuthorize and @RolesAllowed annotations). |
| `@AuthenticationPrincipal` | Injects the presently authenticated user into a class or method as an authentication object. |

<hr />  

## 9. <a name="spring-testing">Spring Testing</a>

**Overview:** The Spring Framework's Inversion of Control (IoC) principles and support for class constructors and setter methods allow for well-defined (such as in the case of wiring beans) and easily implemented unit and integration testing (especially when utilizing a test-driven development (TDD) approach).
<br />
  
**Essential Annotations include:**
| Annotation | Explanation |
| -------- | -------- |
| `@SpringBootTest` | Loads the Spring context so that it can be integration tested. |
| `@WebMvcTest` | Concentrates Spring MVC testing onto specific components/beans. |
| `@TestConfiguration` | Establishes configuration classes for specified tests. |
| `@DataJpaTest` | Consults an in-memory database for JPA repository testing. |
| `@MockBean` | Establishes new mock beans for the Spring context. |
  
<hr />
  
## 10. <a name="supplemental">Supplemental Resources</a>
  
* [Intro to Spring Boot Guide](https://github.com/chaseofthejungle/intro-to-spring-boot)
* [Official Spring Website](https://spring.io/)
  
<hr />
  
TODO #1: Add overview sections and annotations tables for Spring Core, Spring Data, and Spring MVC.  
TODO #2: Add code examples for annotations (as separate text files, linked to from this file), including one file for each category of annotation (9 files of code in total).
