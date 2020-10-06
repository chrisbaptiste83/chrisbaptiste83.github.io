---
layout: post
title:      "Angular Modules Intro"
date:       2020-10-05 03:18:04 -0400
permalink:  angular_modules_intro
---

### What is a module? 

#### In Angular, modules are containers for specific parts of an application. Using modules allows us to separate our application into logical chunks that can be re-used. It is generally recommended that you create modules for each feature in your application, each reusable component, and one to use as a base module for the application. 

### How does Angular know about our modules? 
#### When we create a module in Angular, the angular object we start with is the Angular core. This is Angular's core API which allows us to create and load modules using angular.module. Take a look at the exmple below: 

<script src="https://gist.github.com/chrisbaptiste83/e30f80caad25fe190eea37b3430c9fa9.js"></script> 

#### In the example above, we are telling Angular that we want to create a module named firstModule by providing the empty array in the second parameter. This is an important thing to note as not providing it would tell Angular that we would like to retrieve it, rather than create it. The number of parameters, is true for anything we set/get in Angular. If we have one parameter, we are telling Angular to get whereas if we have two parameters we are telling Angular to set. For example, if we were to want to enable a downloaded plugin to work in conjunction with our firtModule, we would insert the name of the plugin inside the empty array in the second parameter. 


#### Angular apps are modular and Angular has its own modularity system called NgModules. NgModules are containers for a cohesive block of code dedicated to an application domain, a workflow, or a closely related set of capabilities. They can contain components, service providers, and other code files whose scope is defined by the containing NgModule. They can import functionality that is exported from other NgModules, and export selected functionality for use by other NgModules.


