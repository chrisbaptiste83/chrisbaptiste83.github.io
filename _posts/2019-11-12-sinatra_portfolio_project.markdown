---
layout: post
title:      "Sinatra: Implementing User Authentication with Bcrypt"
date:       2019-11-12 10:35:50 -0500
permalink:  sinatra_portfolio_project
---

## Introduction
Designing a Model-View-Controller application and working with both the front and back end components was something that I was always looking forward to do at the start of my journey towards becoming a software developer. Getting exposed to Sinatra and building my first application with it has provided me with a learning experience unlike no other that has only increased my desire to learn more about application development. For my Sinatra project, I created an application that keeps track of a collection of cocktail recipes uploaded by many users. A user can sign up for an account by providing a desired username, password, and email. Once a users sign up and log in, they are then able to upload, edit, and share cocktail recipes with the rest of the application's users.  
## Why User Authentication 
User authentication is the verification of an active human-to-machine transfer of credentials required for confirmation of a user's authenticity. Nowadays, user authentication in applications has become so common that it is hard to image an application without it. User authentication enables a user's information to be safely secured in an appllication's database and enables that information to be retrieved only by users that are authorized to do so based on their credentials.  However,  when you consider how rack based applications like Sinatra depend on stateless HTTP requests that have no association with each other, it becomes inevitable to wonder how exactly these applications are able to identify their users. 

## Getting Started  
### Password_digest column 
The first step is to add a password_digest column to our users table in our application's database. Our user model is required to have the password_digest attribute in order for the authentication process to take place.  

#### My User Migration and Schema: 
<script src="https://gist.github.com/chrisbaptiste83/f77606e4bdfcc5afdc1a9270595a623a.js"></script>


### has_secure_password 
The next step is to modify our user model to include the has_secure_password macro which will provide it with access to various methods that are vital for user authentication. More information on these methods and the has_secure_password can be found [here](https://api.rubyonrails.org/classes/ActiveModel/SecurePassword/ClassMethods.html). 

#### My App's User Model: 
<script src="https://gist.github.com/chrisbaptiste83/d4901a9036bb6f12938650a41802e007.js"></script>  


### Bcrypt gem 
The bcrypt gem works in conjuction with the has_secure_password macro and the password digest column. The next step is to add it to the application's gemfile and to run bundle install to install it. Or you can just enter gem install bcrypt in your terminal when you are within your application's directory.

## Controller Actions 
Our users controller would then have to be modified to work with our session cookies in order for users to be uniquely identified by our application. Additionally, a sessions controller would also need to be created to handle the action of a user logging into the application. I also created some helper methods that I placed in my application controller to identify whether a user is logged in or not.  

### User Controller  
<script src="https://gist.github.com/chrisbaptiste83/76cb75710839575436c6e7044a30e834.js"></script> 

My user controller contains conditional statements in both the signup and profile (/user) routes to check if a user is logged in or not based on the helper methods that are defined in the application's controller. As you can see, when users are created, their user id's get stored as keys in the session hash (line 27). This is what is used by our application to identify users when they log in, as evidenced by our login action in our sessions controller below. 

### Sessions Controller 
<script src="https://gist.github.com/chrisbaptiste83/956c764984226c717e1250d26a5998c3.js"></script> 

Line 14 shows a user's credentials being authenticated and then the user is being identified by our application using the user.id. If you look closely, you'll notice that both controllers use helper methods to redirect users depending on whether they are logged in or not. I defined these helper methods in the application controller. 

### Application Controller 
<script src="https://gist.github.com/chrisbaptiste83/6778f4ee476598a38284e1e72758aaeb.js"></script>  

## Conclusion 
In Sinatra, user authentication is generally accomplished by incorporating the has_secure_password macro in our user model and modifying out actions to handle the logic associated with users loggin in and out. When users are created, their user id is stored in the session hash. This enables our application to identify users when they log in later on. 

##### Check out my Github repo [here](https://github.com/chrisbaptiste83/sinatra-cocktail-app).






