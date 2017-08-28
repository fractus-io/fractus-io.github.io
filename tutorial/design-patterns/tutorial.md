---
layout: page
title: Design Patterns Tutorial
permalink: /tutorials/design-patterns/
tags: design patterns
---

Table of context

* [Singleton](#Singleton)
* [Prototype](#Prototype)
* [Prototype](/Adapter)


##  <a id="Singleton"></a>Singleton 

###  <a id="Story"></a>Story 

* [Story](#Story)
* [Image](#Image)
* [UML](#UML)
* [Implementation](#Implementation)
* [Usage](#Usage)


###  <a id="Story"></a>Story 

Singleton ensures that only one(single) object can be created from the class.

Men's 100 meters world record holder is a singleton.
There can be at most one active "Men's 100 meters world record holder" at any given time. 
Regardless of who that person is the title, "Men's 100 meters world record holder" is a global point of access that identifies the fastes person in the world.





###  <a id="Image"></a>Image 


![alt text](http://www.design-patterns-stories.com/assets/img/image/singleton.jpg "Usain Bolt, Men's 100 meters world record holder")  
###### Brick Lane Graffiti Usain Bolt&nbsp;(<a rel='license' href='https://creativecommons.org/licenses/by/2.0/' target='_blank'>CC BY 2.0</a>)&nbsp;by&nbsp;<a xmlns:cc='http://creativecommons.org/ns#' rel='cc:attributionURL' property='cc:attributionName' href='https://www.flickr.com/people/mdpettitt/' target='_blank'>Martin Pettitt</a>



###  <a id="UML"></a>UML
[![](http://www.design-patterns-stories.com/assets/img/uml/singleton.png)](http://www.design-patterns-stories.com/assets/img/uml/singleton.png)

###  <a id="Implementation"></a>Implementation 

#### *Singleton.java* 
```java 
package com.hundredwordsgof.singleton;

/**
 * Singleton class implements singleton pattern. Only one object can be
 * instantiated.
 * 
 */
public class Singleton {

  /**
   * Holds reference to single instance.
   */
  private static Singleton INSTANCE;

  /**
   * Overrides public Constructor.
   */
  private Singleton() {
  }

  /**
   * Creates the instance if it does not yet exist(lazy instantiation).
   * 
   * @return a reference to the single instance.
   */
  public static Singleton getInstance() {
    if (INSTANCE == null) {
      INSTANCE = new Singleton();
    }
    return INSTANCE;
  }
}
```

###  <a id="Usage"></a>Usage 

#### *SingletonTest.java* 
```java 
package com.hundredwordsgof.singleton;

import static org.junit.Assert.assertEquals;
import static org.junit.Assert.assertNotNull;
import org.junit.Test;

/**
 * Test implementation of the Singleton pattern.
 */
public class SingletonTest {

  @Test
  public void testSingleton() {

    // invokes Singleton.getInstance() for first time,
    // object will be created
    Singleton singleton = Singleton.getInstance();
    assertNotNull(singleton);

    // invokes Singleton.getInstance() for second time,
    // reference to the same object will be returned
    Singleton secondSingleton = Singleton.getInstance();
    assertEquals(singleton, secondSingleton);
  }
}
```

##  <a id="Prototype"></a>Prototype 


* [Story](#Story)
* [Image](#Image)
* [UML](#UML)
* [Implementation](#Implementation)
* [Usage](#Usage)


###  <a id="Story"></a>Story 

Clone itself.

Sheep Dolly is the first mammal to be cloned, so Dolly is a duplicate.





###  <a id="Image"></a>Image 


![alt text](http://www.design-patterns-stories.com/assets/img/image/prototype.jpg "Sheep Dolly")  
###### Geni, <a href="https://commons.wikimedia.org/wiki/File:Dolly_the_sheep_2016.JPG">Dolly the sheep 2016</a>, <a href="https://creativecommons.org/licenses/by-sa/4.0/legalcode">CC BY-SA 4.0</a>



###  <a id="UML"></a>UML
[![](http://www.design-patterns-stories.com/assets/img/uml/prototype.png)](http://www.design-patterns-stories.com/assets/img/uml/prototype.png)

###  <a id="Implementation"></a>Implementation 

#### *Prototype.java* 
```java 
package com.hundredwordsgof.prototype;

/**
 * Declares interface to copy it self.
 */
public abstract class Prototype implements Cloneable {

  /**
   * Copy method.
   * 
   * @return copy of the object
   * @throws CloneNotSupportedException
   *           exception
   */
  abstract Prototype copyMe() throws CloneNotSupportedException;

}
```

#### *ConcretePrototype.java* 
```java 
package com.hundredwordsgof.prototype;

public class ConcretePrototype extends Prototype {

  /**
   * Implements Prototype, meaning clone method.
   */
  public Prototype copyMe() throws CloneNotSupportedException {
    return (Prototype) this.clone();
  }
}
```

#### *Client.java* 
```java 
package com.hundredwordsgof.prototype;

/**
 * Creates a new object by asking a Prototype to clone itself.
 */
public class Client {

  private Prototype prototype;

  public Client(Prototype prototype) {

    this.prototype = prototype;
  }

  public Prototype operation() throws CloneNotSupportedException {
    return prototype.copyMe();
  }
}
```

###  <a id="Usage"></a>Usage 

#### *PrototypeTest.java* 
```java 
package com.hundredwordsgof.prototype;

import static org.junit.Assert.assertNotEquals;
import org.junit.Test;

/**
 * Test Prototype pattern.
 */
public class PrototypeTest {

  @Test
  public void testPrototype() throws CloneNotSupportedException {

    // creates object of type Prototype
    Prototype prototype = new ConcretePrototype();
    // creates Client object(Prototype is "injected" via Constructor)
    Client client = new Client(prototype);

    // client creates new object(clone it self) of type Prototype
    Prototype prototypeClone = client.operation();

    // ensure that prototype and it's own clone are not same objects
    assertNotEquals(prototype, prototypeClone);
  }
}
```
