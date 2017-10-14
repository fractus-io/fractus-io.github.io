---
layout: tutorialpage
title: Introduction
permalink: tutorials/springframework/dependency-injection-advanced
path: /tutorials/springframework/
repo: https://github.com/fractus-io/spring-tutorial
tags: springframework, dependency injection
---

### Dependency Injection Advanced

---

#### Topics
* Dependency Injection (DI)
  * Bean Life Cycle Management
  * ApplicationContext

---

### Bean Life Cycle Management

* beans can be constructed on a way that they receive notifications at certain points in their life cycles
* enables your beans to perform relevant processing at certain points throughout their lives
* two life cycle events 
  * postinitialization 
  * predestruction
  
---

### Bean Life Cycle Management

* postinitialization 
  * after setting property values and after finising dependency checks
* predestruction 
  * before Spring destroys the bean instance
* works only with singletons

---

### PostInitialization

* specifying an Initialization Method

```Java
public class InitDestroyBean {
	...	
	public void init(){	... }	
	...
	
   // <bean id="initDestroyBean" class="...InitDestroyBean" 
   //          init-method="init" destroy-method="destroy">
   //    ...
   // </bean>
}
```

---

### PostInitialization

* executing a Method When a Bean Is Destroyed

```Java
public class InitDestroyBean {
	...
	public void destroy(){ ... 	}
	
   // <bean id="initDestroyBean" class="...InitDestroyBean" 
   //           init-method="init" destroy-method="destroy">
   //    ...
   // </bean>
}
```
---

### PostInitialization

* implementing InitializingBean Interface

```Java
public class InitializingDisposableBean implements InitializingBean {
	...
	public void afterPropertiesSet(){ ... 	}
	
   // <bean id="initializingDisposableBean" 
   //       class="...InitializingDisposableBean"> 
   //  ...
   // </bean>
}
```

---

### PostInitialization

* implementing DisposableBean Interface

```Java
public class InitializingDisposableBean implements DisposableBean {
	...
	public void destroy(){ ... 	}
	
   // <bean id="initializingDisposableBean" 
   //       class="...initializingDisposableBean">
   //    ...
   // </bean>
}
```

---

### Spring Aware Beans

* BeanNameAware makes the object aware of its bean name

```Java
public class BeanNameAwareBean implements BeanNameAware {
	...
	public void setBeanName(){ ... 	}
	
   // <bean id="beanNameAwareBean" 
   //       class="...BeanNameAwareBean">
   // </bean>
}
```

---

### Spring Aware Beans

* BeanFactoryAware gives the bean access to the BeanFactory that created the bean

```Java
public class BeanFactoryAwareBean 
             implements BeanFactoryAware {
	...
	public void setBeanFactory(){ ... 	}
	
   // <bean id="beanFactoryAwareBean" 
   //       class="...BeanFactoryAwareBean">
   // </bean>
}
```

---

### Beans Factory Post Processing

* provides a way for applications to modify their Spring context�s bean definitions before any beans get created 

```Java
public class BeanFactoryPostProcessorBean 
             implements BeanFactoryPostProcessor {
	...
	public void postProcessBeanFactory(...){ ... 	}
	
   // <bean id="beanFactoryPostProcessorBean" 
   //       class="...BeanFactoryPostProcessorBean">
   // </bean>
}
```

---

### Beans Post Processor

* perform additional processing immediately before and after Spring instantiates the bean
  
```Java
public class MyBeanPostProcessor 
             implements BeanPostProcessor {
	...
	public Object postProcessBeforeInitialization(...){ ... }
	
	public Object postProcessAfterInitialization(...){ ... }
	
   // <bean id="myBeanPostProcessor" 
   //       class="...MyBeanPostProcessor">
   // </bean>
}
```

---

### Application Context

* extension of the BeanFactory interface
* enables enterprise-specific features such as transactions and AOP
* providing extra features over BeanFactory

---

### Application Context

* features over BeanFactory
  * additional life-cycle interfaces
  * event propagation to beans implementing the ApplicationListener interface
  * MessageSource, providing access to messages in, i18n-style
  * access to resources, such as URLs and files
  * loading of multiple (hierarchical) contexts

  
---

### Application Context

* when to use
  * always use ApplicationContext over BeanFactory to take advantage of its extended functionality
  * except for a few limited situations such as perhaps in an Applet, where memory consumption might be critical

  
---

### Application Context

* Usage
  * ApplicationContext can be used in a declarative fashion(e.g. ContextLoader in J2EE webapp)
  * can be created programmatically as well
  
```Java
...
ApplicationContext applicationContext = new ClassPathXmlApplicationContext("applicationcontextaware-context.xml");
...

```