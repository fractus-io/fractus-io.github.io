---
layout: tutorialpage
title: Introduction
permalink: /tutorials/springframework/introduction/
path: /tutorials/springframework/
repo: https://github.com/fractus-io/spring-tutorial
tags: springframework
---

### Introduction to Spring Framework

Topics

* Spring History
* What is Spring
* Why Spring 
* Spring architecture

---

### Spring History

* Started 2002/2003 by Rod Johonson and Juergen Holler
* Started as a framework developed around Rod Johnson&#39;s book [Expert One-on-One J2EE Design and Development](https://www.amazon.com/Expert-One-One-Design-Development/dp/0764543857)
* Spring 1.0 Released March 2004
* ...
* Spring 4.2.0 Released July 2015


---

### What is Spring

* Spring Framework is an open source light-weight application framework that aims to make J2EE developement eaisier.
* Spring aims to help whole applications in a consistent and productive manner
* Used for building Java SE & Java EE applications


---

### What is Spring - Key Features

* JavaBeans-based configuration management, applying Inversion-of-Control principles, specifically using the Dependency Injection technique.
* A core bean factory, which is usable globally
* Generic abstraction layer for database transaction management
* Built-in generic strategies for JTA and a single JDBC DataSource


---

### What is Spring - Key Features

* Integration with persistence frameworks Hibernate, JDO and iBATIS
* MVC web application framework, built on core Spring functionality, supporting many technologies for generating views, including JSP, FreeMarker, Velocity, Tiles, iText, and POI
* Extensive aspect-oriented programming(AOP) 


---

### Why Spring

* Problems with Traditional Approach to J2EE ...
  * The EJB component model is complex
  * EJB is designed for distributed, transactional applications. While all non-trivial applications are transactional, distribution should not be built into basic component model
  * J2EE applications are hard to unit test

---

### Why Spring

* Responses to problems was tool support to catch up with J2EE specifications, e.g code generations tools
* Spring aims to take away problems, by simplifying the programming model, rather than concealing complexity behind the complex layer of the tools
* The essence of the Spring is in providing eneterpise sevices to Plain Old Java Object(POJOs). This is valuable in a J2EE enviroment, but application code delivered as POJOs is naturally resuable in variety or runtime enviroments


---

### Why Spring

* Wiring of components through Dependency Injection
* Design to interfaces
* Test-Driven Development (TDD)
* POJO classes can be tested without being tied up with the framework

+++

* Declarative programming through AOP
  * Integration with other technologies
  * EJB for J2EE
  * Hibernate, iBatis, JDBC (for data access)
  * Velocity (for presentation)
  * Struts and WebWork (For web)


---

### Overview of the Spring Framework

* Inversion of Control container
  * Dependecy Injection
* Aspect-Oriented Programming(AOP) framework
* Data Access abstracion
* JDBC simplification

+++

* Transation Management
* MVC web framework
* Simplification for working with JNDI, JTA
* Lightweight remoting
* JMS support
* Support for testing

---

### Overview of the Spring Framework

![](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/images/spring-overview.png.pagespeed.ce.XVe1noRCMt.png)


---

### Overview of the Spring Framework - Core Package

* Core package is the most fundamental part of the framework and provides the IoC and Dependency Injection features
* The basic concept here is the BeanFactory, which provides a sophisticated implementation of the factory pattern which removes the need for programmatic singletons and allows you to decouple the configuration and specification of dependencies from your actual program logic


---

### Overview of the Spring Framework - DAO Package

* The DAO package provides a JDBC-abstraction layer that removes the need to do tedious JDBC coding and parsing of database-vendor specific error codes
* The JDBC package provides a way to do programmatic as well as declarative transaction management, not only for classes implementing special interfaces, but for all your POJOs (plain old Java objects)


---

### Overview of the Spring Framework - ORM Package

* The ORM package provides integration layers for popular object-relational mapping APIs, including JPA, JDO, Hibernate, and iBatis.
* Using the ORM package you can use all those O/R-mappers in combination with all the other features Spring offers, such as the simple declarative transaction management feature mentioned previously


---

### Overview of the Spring Framework - AOP Package

* Spring&#39;s AOP package provides an AOP Alliance-compliant aspect-oriented programming implementation allowing you to define, for example, method-interceptors and pointcuts to cleanly decouple code implementing functionality that should logically speaking be separated
* Using source-level metadata functionality you can also incorporate all kinds of behavioral information into your code


---

### Overview of the Spring Framework - MVC Package

* Spring&#39;s MVC package provides a Model-View-Controller (MVC) implementation for web applications
* Spring&#39;s MVC framework is not just any old implementation; it provides a clean separation between domain model code and web forms, and allows you to use all the other features of the Spring Framework
