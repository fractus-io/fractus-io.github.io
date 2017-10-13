---
layout: tutorialpage
title: Dependency Injection Basics
permalink: /tutorials/springframework/dependency-injection-basics/
path: /tutorials/springframework/
repo: https://github.com/fractus-io/spring-tutorial
tags: springframework
---

### Dependency Injection Basics

---

#### Topics
* Dependency Injection (DI)
  * BeanFactory
  * Autowiring
  * ApplicationContext

---

### DI Basic Concept

* A kind of Inversion of Control (IoC)
* Hollywood Principle:
  * Don&#39;t call me, I&#39;ll call you
* Container resolves (injects) dependencies of components by setting implementation object (push)
* Martin Fowler calls Dependency Injection

---

### DI Basic Concept

* Flexible
  * Avoid adding lookup code in business logic
* Testable
  * No need to depend on external resources or containers for testing
* Maintainable
  * Allows reuse in different application environments by changing configuration files instead of code
 
---

### DI Basic Concept

Two Dependency Injection Variants

* Constructor DI
  * Dependencies are provided through the constructors of the component
* Setter DI
  * Dependencies are provided through the JavaBean style setter methods of the component
  * More popular than Constructor dependency injection
   
---

### DI Basic Concept

Constructor  Dependency Injection

```Java
public class ConstructorBean {

	private String valueToInject;
	
	public ConstructorBean(final String valueToInject){
		this.valueToInject = valueToInject;
	}
}
```
   
---

### DI Basic Concept

Setter  Dependency Injection

```Java
public class SetterBean {

	private String valueToInject;

	public void setValueToInject(String valueToInject) {
		this.valueToInject = valueToInject;
	}		
}
```
  
---

### DI in Spring

#### Sub-topics

* BeanFactory Interface
* XmlBeanFactory implementation
* Bean Configuration file
  * Setter DI
  * Constructor DI
* Beans
* Injection parameters

  
---

### DI in Spring

BeanFactory

* BeanFactory object is responsible for managingbeans and their dependencies
* Your application interacts with Springs DI container through BeanFactory interface
  * BeanFactory object has to be created by the application typically XmlBeanFactory

+++  

  * BeanFactory object, when it gets created, reads bean configuration file and performs the wiring
  * Once created, the application can access the beans via BeanFactory interface

  
---

### DI in Spring

BeanFactory Implementations

* XmlBeanFactory 
  * Convenience extension of DefaultListableBeanFactory that reads bean definitions from an XML document
   
---

### DI in Spring

Reading Xml Config file via XmlBeanFactory class 

```Java
public class XmlConfigWithBeanFactory {
  
	public static void main(String[] args) {
    
		XmlBeanFactory factory = 
			new XmlBeanFactory(new FileSystemResource("beans.xml"));
		SomeBeanInterface b = 
			(SomeBeanInterface) factory.getBean("nameOftheBean";
  
	}
}
```
   
---

### DI in Spring

BeanFactory Configuration File
*  Each bean is defined using <span style="color:red">bean</span> tag under the root of the <span style="color:red">beans</span> tag 
*  The <span style="color:red">id</span> attribute is used to give the bean its default name 
*  The <span style="color:red">class</span> attribute specifies the type of the bean

   
---

### DI in Spring

Example: Setter DI 

```Java
public class SetterBean {

	private String valueToInject;

	public void setValueToInject(String valueToInject) {
		this.valueToInject = valueToInject;
	}		
}

// <bean id="setterBean" 
//	class="io.fractus.springframework.tutorial.dependency.injection.setterdi.SetterBean">    	
//	 <property name="valueToInject" value="value injected via setter"></property>
// </bean>

```
  
---

### DI in Spring

Example: Constructor DI 

```Java
public class ConstructorBean {

	private String valueToInject;
	
	public ConstructorBean(final String valueToInject){
		this.valueToInject = valueToInject;
	}
}

// <bean id="constructorBean" 
//  class="io.fractus.springframework.tutorial.dependency.injection.constructordi.ConstructorBean">
//     <constructor-arg value="value injected via constructor"/>
// </bean>

```
   
---

### DI in Spring

Beans
*  The term &#34;bean&#34; is used to refer any component managed by the BeanFactory
*  The &#34;beans&#34; are in the form of JavaBeans (in most cases)
  *  no arg constructor
  *  getter and setter methods for the properties

+++

*  Beans are singletons by default
*  Properties the beans may be simple values or references to other beans
*  Beans can have multiple names

   
---

### DI in Spring

Injection ParameterTypes

*  Spring supports various kinds of injection parameters
  *  Simple Values
  *  Beans in same factory
  *  Beans in another factory
 
+++

  *  Collections
  *  Externally defined properties
*  You can use these types for both setter and constructor injections
  
---

### DI in Spring

Injecting Simple Values 

```Java
//    <bean id="injectSimpleValues" 
//	 class="io.fractus.springframework.tutorial.dependency.injection.injectsimplevalues.InjectSimpleValues">	 
//        <property name="name">
//            <value>dstar55</value>
//        </property>
//        <property name="year">
//            <value>2017</value>
//        </property>
//        <property name="height">
//            <value>9.99</value>
//        </property>
//        <property name="springFun">
//            <value>true</value>
//        </property>
//        <property name="yearInSeconds">
//            <value>1103760000</value>
//        </property>
...

```
  
---

### DI in Spring

Bean Naming
*  Each bean must have at least one name that is unique within the containing BeanFactory
*  A bean can have multiple names
  *  Specify comma or semicolon-separated list of names in the name attribute

+++

*  Name resolution procedure
  *  If a &#60;bean&#62; tag has an id attribute, the value of the id attribute is used as the name
  *  If there is no id attribute, Spring looks for name attribute
  *  If neither id nor name attribute are defined, Spring use the class name as the name
  
---

### DI in Spring

Bean Naming Example

  
---

### DI in Spring

Autowiring Properties
* Beans may be auto-wired (rather than using &#60;ref&#62;)
  *  Per-bean attribute autowire
  *  Explicit settings override
*  autowire=&#34;byName&#34;
  *  Bean identifier matches property name

+++

*  autowire=&#34;byType&#34;
  *  Type matches other defined bean
*  autowire=&#34;constructor&#34;
  *  Match constructor argument types
*  autowire=&#34;autodetect&#34;
  *  Attempt by constructor, otherwise &#34;type&#34;

  
---

### DI in Spring

Benefits of Dependency Injection
*  Frees your object from resolving dependencies
*  Simplifies your code
*  Improves code reusability
*  Promotes programming to interfaces
*  Improves testability
*  Opens the door for new possibilities(control over life cycle)


