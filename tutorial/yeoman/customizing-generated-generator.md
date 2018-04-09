---
layout: tutorialpage
title: Customizing generated generator
permalink: /tutorials/yeoman/customizing-generated-generator/
path: /tutorials/yeoman/
repo: https://github.com/fractus-io/yeoman-tutorial
tags: yeoman
---

Next delete the dummyfile.txt from the template folder and open the **index.js** and modify such that you only see the following code:

```java
var yeoman = require('yeoman-generator');
var chalk = require('chalk');
var yosay = require('yosay');
 
 
module.exports = class extends Generator {
  prompting() {
	  
    // Have Yeoman greet the user.
    this.log(
      yosay(`Hello, this is yet another code generator`)
    );

	//Here, we will as questions from the user.
    const prompts = [
      {

      }
    ];

	//Here, we will save the data from the user for later use as we will see shortly
    return this.prompt(prompts).then(props => {
      // To access props later use this.props.someAnswer;
	  this.appName = props.myApp;     //The value of myApp variable is stored in appName to used in Layout page.
      this.props = props;
    });
  }

  //Here, we will output our project files when the generator runs.
  writing() {
  }

  //Here, we will output our project files when the generator runs.
  install() {

  }
};
 
```

Our generator will have following actions:

* Display a welcome message
* Take inputs from the user
* Generate project files
* Install dependencies

##### Display a welcome message

Here you will write a message which will be shown when generator is started.

```
this.log(yosay('Hello, this is yet another code generator')); 
```

##### Take inputs from the user

In the next step, you have to take inputs from the user. 
These inputs can be a bool (yes\no), a number or it can be a string. 
Here I'll be using just string input and this can be done in the prompt section of the code as:

```
 var prompts = [{
    type: 'input',                                //Type of the input
    name: 'myApp',                                //Variable name, that will be use later in _Layout.cshtml for title
    message: 'What should be your app name?',     //Message for getting input
    default: 'App'                                //Default value of input if the user did not specify any
  }];
  
```


Now we have to preserve this tiny user input to be used later in the project. The user input will be used to be displayed in the layout page and in the title. This can be done in this section:

```java
 return this.prompt(prompts).then(function (props) {
     this.appName = props.myApp;     //The value of myApp variable is stored in appName to used in Layout page.
     this.props = props;
 }.bind(this));
```
 

##### Generate project files

In order to generate the files from the source (In the generator's template folder) to destination (Where the generator is called), 
it is recommended that you should name them separately. One way is to put "_" before each file name in the source and remove this while generating in the target destination. 
For this example, rename each file by putting the "_" before and remove the "." with some files only with extensions such as .gitignore and others.

So, in order to copy dummyfile.txt we should do following:

```java
  writing() {
    this.fs.copy(
      this.templatePath('_dummyfile.txt'),
      this.destinationPath('dummyfile.txt')
    );
  }
```

In principle there are two methods for coping, `copy()` and `copyTpl()` that are used to the copy 
the templates from our template path to a destination path.

The difference between the two methods is that `copyTpl()` takes a third parameter 
which is a list of data to be bound to the template file after it is generated while 
`copy()` is used when there are no bindings required in the template.   
Example:

```java
  writing() {
	  
	// copy dummfile.txt without argument  
    this.fs.copyTpl(
      this.templatePath('_dummyfile.txt'),
      this.destinationPath('dummyfile.txt')
    );
	  
	// copy dummfile.txt with argument  
    this.fs.copyTpl(
      this.templatePath('_dummyfile-arg.txt'),
      this.destinationPath('dummyfile-arg.txt'), {
         name: this.props.name
      }
    );
  }
```

If we are using `copyTpl()`, then the value which are bind can be used in template file:

```java
  writing() {
	  	  
	// copy dummfile.txt with argument  
    this.fs.copyTpl(
      this.templatePath('_dummyfile-arg.txt'),
      this.destinationPath('dummyfile-arg.txt'), {
         name: this.props.name
      }
    );
  }
```

_dummyfile-arg.txt:
```
"name": "<%= name %>"
```

will generate:
```
"name": "App"
```
