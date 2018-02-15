## Spring Questions
*********************
#### 612. What is Spring framework?
Spring is development framework for Java programming. It is an open source development framework for Enterprise Java.
The core features of Spring Framework can be used in developing a Java Enterprise application.
It has many extensions and jars for developing web applications on top of Java EE platform.
With Spring we can develop large-scale complex Java applications very easily. It is also based on good design patterns like
Dependency Injection, Aspect oriented programming for developing extensible feature rich software.

#### 613. What are the benefits of Spring framework in software development?
Many benefits of Spring framework are:
1. **Lightweight Framework:** Basic Spring framework is very small in size. It is easy to use and does not add a lot of overhead on software. It just has 2 MB in basic version.
2. **Container:** Spring framework provides the basic container that creates and manages the life cycle of application objects like Plain old Java objects (POJO). It also stores the configuration files of application objects to be created.
3. **Dependency Injection (DI): **Spring provided loose coupling is application by Dependency Injection. It uses Inversion of Control technique by which objects specify their dependencies to Spring container instead of creating new objects themselves.
4. **Aspect Oriented Programming (AOP):** Spring framework promotes and provides support for Aspect oriented programming in Java. This helps in separating application business logic from system services that are common across all the business logic. E.g. Logging can be a cross cutting concern in an Application.
5. **Transaction Management:** Spring provides a framework for transaction management. So a developer does not have to implement it from scratch. Spring Transaction Management is so powerful that we can scale it from one local transaction to global transactions in acluster.
6. **MVC Framework:** For Web applications, Spring provides MVC framework. This framework is based on MVC design pattern andhas better features compared to other web frameworks.
7. **Exception Handling:** Spring also gives support for a common API to handle exceptions in various technologies like- Hibernate, JDBC etc.

#### 614. What are the modules in Core Container of Spring framework?
Spring framework has a Core Container. Modules in Core Container are:
Core module
Bean module
Context module
Spring Expression Language module

![Spring Module](https://www.javatpoint.com/images/sp/spmodules.jpg)


#### 615. What are the modules in Data Access/Integration layer of Spring framework?
Modules in Data Access/Integration Layer of Spring framework are:
1. **JDBC module:** An abstraction layer to remove tedious JDBC coding.
2. **ORM module** Integration layers for Object Relational Mapping
3. **OXM module:** An abstraction layer to support Object XML mapping.
4. **Java Messaging Service (JMS) module:** Module for producing and consuming messages.
5. **Transactions module:** Transaction Management for POJO classes.

#### 616. What are the modules in Web layer of Spring framework?
Modules in Web Layer of Spring framework are:
1. **Web module:** This provides basic web-oriented integration features.
2. **Servlet module:** Support for Servlet Listeners.
3. **WebSocket module:** Support for Web Socket style messaging.
4. **Portlet module:** MVC implementation for Portlet environment.

#### 617. What is the main use of Core Container module in Spring framework?
As the name suggests, Spring Core Container is the core of Spring framework. It gives the basic functionality of the Spring. All the parts of Spring Framework are built on top of Core Container. Its main use is to provide Dependency Injection (DI) and Inversion
of control (IOC) features.

#### 618. What kind of testing can be done in Spring Test Module?
Spring Test Module provides support for Unit testing as well as Integration testing of Spring components. It allows using JUnit or TestNG testing frameworks. It also gives ability to mock objects to use the test code.
#### 619. What is the use of BeanFactory in Spring framework?
BeanFactory is the main class that helps in implementing Inversion of Control pattern in Spring. It is based on the factory design pattern. It separates the configuration and dependencies of an
application from the rest of application code. Implementations of BeanFactory like XmlBeanFactory class are used by applications built with Spring.
#### 620. Which is the most popular implementation of BeanFactory in Spring?
XMLBeanFactory is the BeanFactory in Spring. most popular implementation of Spring.

#### 621. What is XMLBeanFactory in Spring framework?
XMLBeanFactory is one of the most useful implementation of BeanFactory in Spring. This factory loads its beans based on the definitions mentioned in an XML file. Spring container reads bean configuration metadata from an XML file and creates a fully configured application with the help of XMLBeanFactory class.
#### 622. What are the uses of AOP module in Spring framework?
AOP module is also known as Aspect Oriented Programming module. Its uses are:
Development of aspects in a Spring based application Provides interoperability between Spring and other frameworks Supports metadata programming to Spring AOP.
#### 623. What are the benefits of JDBC abstraction layer module in Springframework?
Spring provides JDBC abstraction layer module. Main benefits of this module are:
Helps in keeping the database code clean and simple. Prevents problems that result from a failure to close database resources.

Provides a layer of useful exceptions on top of the error messages given by different database servers. Based on Spring’s AOP module Provides transaction management services for objects in a Spring application
#### 624. How does Spring support Object Relational Mapping (ORM) integration?
#### 625. How does Web module work in Spring framework?
#### 626. What are the main uses of Spring MVC module?
#### 627. What is the purpose of Spring configuration file?
#### 628. What is the purpose of Spring IoC container?
#### 629. What is the main benefit of Inversion of Control (IOC) principle?
#### 630. Does IOC containers support Eager Instantiation or Lazy loading of beans?
#### 631. What are the benefits of ApplicationContext in Spring?
#### 632. How will you implement ApplicationContext in Spring framework?
#### 633. Explain the difference between ApplicationContext and BeanFactory in Spring?
#### 634. Between ApplicationContext and BeanFactory which one is preferable to use in Spring?
#### 635. What are the main components of a typical Spring based application?
#### 636. Explain Dependency Injection (DI) concept in Spring framework?
#### 637. What are the different roles in Dependency Injection (DI)?
#### 638. Spring framework provides what kinds of Dependency Injection mechanism?
#### 639. In Spring framework, which Dependency Injection is better? Constructor-based DI or Setter-based DI?
#### 640. What are the advantages of Dependency Injection (DI)?
#### 641. What are the disadvantages of Dependency Injection (DI)?
#### 642. What is a Spring Bean?
#### 643. What does the definition of a Spring Bean contain?
#### 644. What are the different ways to provide configuration metadata to a Spring Container?
#### 645. What are the different scopes of a Bean supported by Spring?
#### 646. How will you define the scope of a bean in Spring?
#### 647. Is it safe to assume that a Singleton bean is thread safe in Spring Framework?
#### 648. What are the design-patterns used in Spring framework?
#### 649. What is the lifecycle of a Bean in Spring framework?
#### 650. What are the two main groups of methods in a Bean’s lifecycle?
#### 651. Can we override main lifecycle methods of a Bean in Spring?
#### 652. What are Inner beans in Spring?
#### 653. How can we inject a Java Collection in Spring framework?
#### 654. What is Bean wiring in Spring?
#### 655. What is Autowiring in Spring?
#### 656. What are the different modes of Autowiring supported by Spring?
#### 657. What are the cases in which Autowiring may not work in Spring framework?
#### 658. Is it allowed to inject null or empty String values in Spring?
#### 659. What is a Java-based Configuration in Spring?660.What is the purpose of @Configuration annotation?
#### 661. What is the difference between Full @Configuration and 'lite' @Beans mode?
#### 662. In Spring framework, what is Annotation-based container configuration?
#### 663. How will you switch on Annotation based wiring in Spring?
#### 664. What is @Autowired annotation?
#### 665. What is @Required annotation?
#### 666. What are the two ways to enable RequiredAnnotationBeanPostProcessor in Spring?
#### 667. What is @Qualifier annotation in Spring?
#### 668. How Spring framework makes JDBC coding easier for developers?
#### 669. What is the purpose of JdbcTemplate?
#### 670. What are the benefits of using Spring DAO?
#### 671. What are the different ways to use Hibernate in Spring?
#### 672. What types of Object Relational Mapping (ORM) are supported by Spring?
#### 673. How will you integrate Spring and Hibernate by using HibernateDaoSupport?
#### 674. What are the different types of the Transaction Management supported by Spring framework?
#### 675. What are the benefits provided by Spring Framework’s Transaction Management?
#### 676. Given a choice between declarative and programmatic Transaction Management, which method will you choose?
#### 677. What is Aspect Oriented Programming (AOP)
#### 678. What is an Aspect in Spring?
#### 679. In Spring AOP, what is the main difference between a Concern and a Cross cutting concern?
#### 680. What is a Joinpoint in Spring AOP?
#### 681. What is an Advice in Spring AOP?
#### 682. What are the different types of Advice in Spring AOP?
#### 683. What is a Pointcut in Spring AOP?
#### 684. What is an Introduction in Spring AOP?
#### 685. What is a Target object in Spring AOP?
#### 686. What is a Proxy in Spring AOP?
#### 687. What are the different types of AutoProxy creators in Spring?
#### 688. What is Weaving in Spring AOP?
#### 689. In Spring AOP, Weaving is done at compile time or run time?
#### 690. What is XML Schema-based Aspect implementation?
#### 691. What is Annotation-based aspect implementation in Spring AOP?
#### 692. How does Spring MVC framework work?
#### 693. What is DispatcherServlet?
#### 694. Can we have more than one DispatcherServlet in Spring MVC?
#### 695. What is WebApplicationContext in Spring MVC?
#### 696. What is Controller in Spring MVC framework?
#### 697. What is @RequestMapping annotation in Spring?698.What are the main features of Spring MVC?
#### 699. What is the difference between a Singleton and Prototype bean in Spring?
#### 700. How will you decide which scope- Prototype or Singleton to use for a bean in Spring?
#### 701. What is the difference between Setter and Constructor based Dependency Injection (DI) in Spring framework?
#### 702. What are the drawbacks of Setter based Dependency Injection (DI) in Spring?
#### 703. What are the differences between Dependency Injection (DI) and Factory Pattern?
#### 704. In Spring framework, what is the difference between FileSystemResource and ClassPathResource?
#### 705. Name some popular Spring framework annotations that you use in your project?
#### 706. How can you upload a file in Spring MVC Application?
#### 707. What are the different types of events provided by Spring framework?
#### 708. What is the difference between DispatcherServlet and ContextLoaderListener in Spring?
#### 709. How will you handle exceptions in Spring MVC Framework?
#### 710. What are the best practices of Spring Framework?
#### 711. What is Spring Boot?