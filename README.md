# Spring Annotations Guide

**Spring Aspect-Oriented Programming (AOP) Overview:** Knowledge of several concepts is essential to understanding the underlying tenets of AOP. These include...
  
*Aspects:* Aspects are classes that implement enterprise app behavior, cutting across more than one class in doing so. There are multiple ways to configure an aspect, such as through XML or using the AspectJ integration.  

*Join Points:* Join points are points/places in apps in which tasks are performed, such as modifying variable values of objects, handling exceptions, and running methods. Join points are 'located' at the execution points of methods.  

*Pointcuts:* Pointcut expressions (using AspectJ pointcut expression language) are associated with join points, and evaluate if an advice is to be executed.  

*Advices:* Advices are actions that are performed for their associated join points. These methods are ran when join points with associated pointcuts are reached in app execution.  

*Target Objects:* Advices are associated with these proxied objects. These use runtime proxies, which means that subclasses are established at runtime (configurations determine which advices are to be applied and target methods are overridden).  

*Proxies:* Proxy classes are established (via JDK dynamic proxy), which are associated with advice markings/invocations and target classes (AOP proxy classes).  

*Weaving:* The tasks that associates aspects with related objects, establishing the advised proxy objects. AOP natively does this at.  

<hr />  
  
**Essential AOP Annotations include:**  
  * `@Aspect`: Marks/indicates that a class is an aspect, and can cut across more than one class (such as for enterprise app implementations).
  * `@Pointcut`: Declares reusable pointcut expressions.
  * `@Before`: Indicates that an advice is to run before a method is executed.
  * `@After`: Indicates that an advice is to run after a method is executed (regardless of which it terminates properly or by throwing an exception).
  * `@Around`: Indicates that an advice wraps around, or surrounds, a method. Invokes a specified join point method.
  * `@AfterThrowing`: Indicates that an advice is to run after a method executes and throws an exception (method does not run properly/normally).
  * `@AfterReturning`: Indicates that an advice is to run after a method executes and returns properly (without throwing an exception).

<hr />  

**Spring Security Overview:** The Spring Security framework includes mechanisms for authentication (such as single sign-on capabilities) and authorization, as well as securing apps against popular web security attacks. 
<hr />
  
**Essential Spring Security Annotations include:**  
  * `@EnableWebSecurity`: Toggles Spring Security to on for the associated app.
  * `@PreFilter`: Provides an expression that, if true, adds a class or method to a security filter chain.
  * `@PostFilter`: Provides an expression that, if determined to be true after a class or method is ran, adds it to a security filter chain.
  * `@Secured`: Defines role-associated security for methods.
  * `@RolesAllowed`: Indicates which roles can access a method.
  * `@PreAuthorize`: Indicates pre-authorization checks for methods.
  * `@PostAuthorize`: Indicates post-authorization checks for methods.
  * `@RoleHierarchy`: States permitted roles, clarifying security configuration (and limiting the need for @PreAuthorize and @RolesAllowed annotations).
  * `@AuthenticationPrincipal`: Injects the presently authenticated user into a class or method as an authentication object.

<hr />  
TODO #1: Add annotations and descriptions for Core, Scheduling, Spring Boot, Spring Cloud, Spring Data, Spring MVC, and Testing.  
  
TODO #2: Add code examples.
