---
layout: post
title:      "Asynchronous Javascript Requests and a Rails API"
date:       2020-04-08 18:09:38 -0400
permalink:  rails_with_javascript
---

## My Rails with Javascript Application: Chris's Cocktails 
### Overview of Completing the Application 

For my Rails with Javascript project, I decided to build an application similar to what I had built for my Rails project. Rather than implementing Javascript to my existing Rails application like I had originally planned to do, I challenged myself to create most of my application's functionality with Javascript. One of the things that I enjoyed learning the most from this module was creating Javascript methods that render html code and then interacting with it. This module provided me with a vast amount of knowledge concerning the application of Javascript in the front end development of web applications. Prior to the start of this module, I was very curious to learn how Javascript methods can influence the appearance of an application and even more so as to how Javascript code could be tested in a browser console or how it is able to target specific html nodes.  

### Project Requirements: Application Functionality and Features

The requirements for this project consisted of having various fetch requests from the front end of the application to the backend that update the backend of the application. I fuflfilled these requirements by implementing various fetch requests to create and read cocktail recipes. Additionally, I implemented fetch requests for creating, editing, and deleting recipe ingredients. My rails backend consists of a has-many relationship between a cocktail model and an ingredient model. Once users that are interacting with my application are viewing a particular cocktail, they are able to create and add ingredients to the cocktail. Once a users are viewing a particular cocktail's show page, they are able to add and delete the recipe's ingredients directly from the show page with only a click of a button.  

## Implementing Asynchronous Javascript Requests into Application 

### What is JSON? 

In a nutshell, JSON is a format that programmers use to send data across the internet. It stands for Javascript Object Notation. Typically, a response from a fetch request is formatted in JSON and a .then method gets chained onto the promise that is returned as callback, and then some more of the application's logic is executed with the response. Here take a look at an example from my app below: 

<script src="https://gist.github.com/chrisbaptiste83/db62f33cd8ed0b5f067404a2ab304b02.js"></script> 

Here we can see that the CocktailAPI class contains the static method that actually conducts the fetch request to my application's API, posting information onto it. This method gets called in static create method in the Cocktail class, and a callback method is chained onto the response creating a new instance of the Cocktail class with the information from the request's response. 

### Types Of Fetch Requests Used in Application 

Here is what my API class looks like. This is the class where all of my application's fetch requests are located: 

<script src="https://gist.github.com/chrisbaptiste83/167f1a904f09fa5fc062c6f8557550c4.js"></script> 

#### Check out my github repo [here](https://github.com/chrisbaptiste83/rails-with-js-project)
