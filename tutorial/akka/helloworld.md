---
layout: page
title: Akka Hello World
permalink: /akka/HelloWorld/
tag: pattern
---

### Creating a "Hello World" actor example

The "Hello World" actor example, as with all "Hello World" applications, is of no real use to anyone,
except to illustrate some really basic concepts. The "Hello World" actor example will show how to
create a project based on akka-actor library including a simple actor, build it, and execute it in the local
environment.

#### How to do it …

1. Create new class *HelloWorldActor*, which extends *UntypedAbstractActor* and implements method *onReceive*.
The *onReceive* method is message handler and will be invoked when message is send to *HelloWorldActor*.
In our case *onReceive* method will implement simple logic which counts the number of the messages and prints the "Hello World" message.

```Java
public class HelloWorldActor extends UntypedAbstractActor {

  private int count = 0;
  
  public void onReceive(Object message) throws Exception {
    count++;
    System.out.println("Received message: " + message + " ! My Count is now: " + Integer.toString(count));
  }

}
```
2. In order to send a message to the *HelloWorldActor*, first we must create **Akka System**:

`ActorSystem actorSystem = ActorSystem.create("aSystem");`

then we must get a *HelloWorldActor* reference from **Akka System**:

`ActorRef helloWorldActorRef = actorSystem.actorOf(Props.create(HelloWorldActor.class), "helloWorldActor");`

and then we can send a message to the *HelloWorldActor*:

`helloWorldActorRef.tell("Hello World", null);`

```Java
public class Main {

  public static void main(String[] args) {
    
    // create an Akka system
    ActorSystem actorSystem = ActorSystem.create("aSystem");
    // create an HelloWorldActor
    ActorRef helloWorldActorRef = actorSystem.actorOf(Props.create(HelloWorldActor.class), "helloWorldActor");
    
    for (int i = 0; i < 10; i++) {
        // send a "Hello World" message to the HelloWorldActor
        helloWorldActorRef.tell("Hello World", null);  
    }
   
    // wait for a second
    Thread.sleep(1000);
    
    // stop the HelloWorldActor
    actorSystem.stop(helloWorldActorRef);
    
    // close the Akka system
    actorSystem.terminate();
  }
```

3. After you have resolved the compiler issues, you can execute the programm by issuing
the following command from the project's root folder:

`mvn compile exec:java -Dexec.classpathScope=compile -Dexec.mainClass=io.fractus.akka.helloworld.Main`


#### How it works ...

As you saw in the console output, the example outputs several "Hello World" messages. 
Let’s take a look what happens at runtime.

First, the main class creates an akka.actor.ActorSystem, a container in which Actors run. 
Next, it creates instance of a *HelloWorldActor*.


The example then sends messages to the *HelloWorldActor*, which counts the number of messages and prints them to the console.




