---
layout: tutorialpage
title: Introduction
permalink: /tutorials/design-patterns/introduction/
path: /tutorials/design-patterns/
repo: https://github.com/dstar55/100-words-design-patterns-java
tags: design patterns
---

* [Overview](#Overview)
* [History](#History)
* [Structure](#Structure)
* [Source Code](#SourceCode)

###  <a id="Overview"></a>Overview 

In software engineering, a software design pattern is a general reusable solution to a commonly occurring problem within a given context in software design. 
Pattern is a description or template for how to solve a problem that can be used in many different situations. 

Design patterns are formalized best practices that the programmer can use to solve common problems when designing an application or system.


###  <a id="History"></a>History 

Patterns originated as an architectural concept by [Christopher Alexander](https://en.wikipedia.org/wiki/Christopher_Alexander) (1977/79). 
In 1987, [Kent Beck](https://en.wikipedia.org/wiki/Kent_Beck) 
and [Ward Cunningham](https://en.wikipedia.org/wiki/Ward_Cunningham) began experimenting with the idea of applying patterns to 
programming – specifically pattern languages – and presented 
their results at the [OOPSLA](https://en.wikipedia.org/wiki/OOPSLA) conference that year.

In the following years, Beck, Cunningham and others followed up on this work.
Design patterns gained popularity in computer science after the 
book [Design Patterns: Elements of Reusable Object-Oriented Software](https://en.wikipedia.org/wiki/Design_Patterns_(book)) was published in 1994 
by the so-called **"Gang of Four"** (Gamma et al.), 
which is frequently abbreviated as **"GoF"**. 

###  <a id="Structure"></a>Structure

Description of design patterns are composed of several sections: 
Pattern Name and Classification, Intent, Also Known As, Motivation (Forces),
Applicability, Structure, Participants, Collaboration, Consequences, Implementation,
Sample Code, Known Uses, Related Patterns.

Since standard structure can be complex for young software engineer, this tutorial describes GoF Design Patterns on a simple way.

Each pattern is described using following triad:

**Understand:** describes a pattern with story from real life

**Implement:** referent implementation of the pattern

**Apply:** discuss where pattern can be(or is) applied

If you are a junior developer, and want to learn Design Patterns, this tutorial is the place to start.
If you are an intermediate or senior developer, and want to improve existing knowledge about Design Patterns, this tutorial can help you too.

###  <a id="SourceCode"></a>Source Code

The full implementation of this tutorial can be found in the [Github Repo](https://github.com/dstar55/100-words-design-patterns-java).
You must have installed [Java](https://java.com/en/download/help/download_options.xml), 
[Maven](https://maven.apache.org/install.html) & 
[Git Client](https://www.linode.com/docs/development/version-control/how-to-install-git-on-mac-and-windows).

Clone repo:

```
$ git clone https://github.com/dstar55/100-words-design-patterns-java .
```

Build:

```
$ mvn clean install -DskipTests=true
```

Run Tests:

```
$ mvn test
```

Note: content of his tutorial is published as dedicated site, [Design Patterns Stories](http://www.design-patterns-stories.com/)
