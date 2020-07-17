---
layout: post
title:      "Ruby Applications and Rack  "
date:       2020-02-04 13:01:19 -0500
permalink:  rails_project
---

## What Is Rack? 
Rack is what is happening behind the scenes in every application built using Rails, Sinatra, and any of the other Ruby frameworks. Rack is the layer between these frameworks and the application server. All web servers have a core architecture in common. By looking at it, we can build a mental model for how all web servers work. All of them  look at an HTTP request and look at the HTTP verb and path and then run some conditional logic to find out which stuff to send back. In Ruby based applications, this process is handled by Rack.  

## Why Do We Use Rack?  
Rack allows for different servers and frameworks to be interchangeable. They become components that you can then plug in. It really does not matter what framework or server you are using if they implement the Rack interface. With Rack, every component does its job and everyone is happy. 

## Setting Up Rack 
A Rack application is a class with one method: call. However, new instances of the Proc class are run by calling call on them, so one could simply use a Proc. All this method needs to do is return an Array with three elements: An HTTP Status code where 200 is used for OK, a hash with a "Content-Type" key that returns the value (for HTML-based documents) of text/html, and something that responds to each which contains the multiple lines of a document of the "Content-Type"'s type (here, Strings that look like HTML: "<p>Like this!</p>". (Usually an array). It looks like this:

<script src="https://gist.github.com/chrisbaptiste83/6a1621b54bf9fe1532ab39112f3342f4.js"></script> 

This code will start a server on port 8080. The array being returned contains the HTTP status code, the HTTP headers, and the contents ("Hello from Rack). 

## Example of Using Rack Middleware 
The following is an example of chaining a rack application and middleware so they work together: 

### Given the following Rack app:  
<script src="https://gist.github.com/chrisbaptiste83/0d0e9258fb1593d83e34c178687ba40e.js"></script>

 ### And the middleware:  
<script src="https://gist.github.com/chrisbaptiste83/693b13e1d79996ac7ba86331117c43a1.js"></script>
 
 ### This how we combine them together: 
 <script src="https://gist.github.com/chrisbaptiste83/4cdeefab3f05a469ca9e3120547bafa4.js"></script>

In this example, we have two Rack applications.One is for the IP check(FilterLocalHost). The other is for the application itself to deliver the content (HTML,JSON, etc). Notice that @app.call(env), that's what makes FIlterLocalHost a middleware. When this application is ran, one of two things can happen: we can return a response, which stops the middleware chain, or we pass a request along with @app.call(env) to the next middleware, or the app itself. 


