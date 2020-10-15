---
layout: post
title:      "Angular: Directives, Expressions, and Controllers "
date:       2020-10-15 19:42:24 +0000
permalink:  angular_directives_expressions_and_controllers
---


### What is a Directive? 

#### In Agular, a directive is a marker on a DOM element that expands html in a certain manner.  Directives can tell AngularJS to attach a specific behavior to a DOM element or they can completely transform an element and its children.  Angular comes with several built-in directives, and we can also create our own custom ones. For example, the ng-init directive initializes variables in AngularJS, take a look at the example below: 

<script src="https://gist.github.com/chrisbaptiste83/e69f8271c0014b1b37d614201c29e128.js"></script> 



### What is an Expression? 

#### An expression in AngularJS is very similar to an expression in Javascript inside of curly braces. AngularJS evaluates the expression and binds the data to html. Take a look below: 

<script src="https://gist.github.com/chrisbaptiste83/4587b1dc8a0aafeb6827e16ef2f63620.js"></script> 


### What is a Controller? 

#### A Controller is a Javascript function that maintains tha application's data using the $cope object. In Angular, the ng-controller directive is used to specify a controller in an application. Take a look an example below: 
<script src="https://gist.github.com/chrisbaptiste83/01fc204a3e8f5528fa009419579e23d1.js"></script>

