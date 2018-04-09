---
layout: tutorialpage
title: Create custom generator
permalink: /tutorials/yeoman/create-custom-generator/
path: /tutorials/yeoman/
repo: https://github.com/fractus-io/yeoman-tutorial
tags: yeoman
---

Using yeoman we can create our own generators.
This means that you can automatize copy/paste/modify ...

 

First we must install yeoman generator

```
$ npm install -g yo generator-generator
```

now we are ready to create our custom generator

let's make directory where our custom generator will be created

```
$ mkdir mygen
```

move to that directory

```
$ cd mygen
```

then start yo generator

```
$ yo generator
```

answer to the questions and wait

yeoman will ask few questions, such as description, email address, GitHub account and others.

After providing all the information, it will start installing the required NPM dependencies and will generate a directory structure something like this.

```

generator-mygen
  |
  |__app
      |
      |
      |_template
      |    |
      |    |_dummyfile.txt
      |
      |_ index.js 	  

```

now we need to link new generator with command

```
$ npm link
```
This will begin making your generator locally on your machine.

Now you should be able to see new generator in a list of the yo generators

```
$ yo
? 'Allo ds! What would you like to do?
  Generator
  Java
  Jhipster
> Mygen
  ──────────────
  Update your generators
  Install a generator
(Move up and down to reveal more choices)
```

Generator can be invoked with following command as well:

```
$ yo mygen
```

it will generate dummyfile.txt


