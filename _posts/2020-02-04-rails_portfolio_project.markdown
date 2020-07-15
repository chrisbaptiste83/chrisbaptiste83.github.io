---
layout: post
title:      "Partials and Scope Methods in Rails"
date:       2020-02-04 12:58:14 -0500
permalink:  rails_portfolio_project
---

## Introduction 
Completing my Rails project has made me realize why rails is very popular among software developers and has given me a glimpse of some of its amazing magic-like capabilities. For my project, I decided to create a cocktail recipe tracker application. I had previously done a cocktail recipe tracker with my Sinatra Project and wanted to use the same concept with Rails in order to compare my experiences with both frameworks.  
## Partials
One of the things that I enjoyed doing the most during this project was incorporating partials in order to more effectively structure and organize my code. In Rails, a partial is a file that is part of a larger view. To indicate that this file is a partial, an underscore is prefixed to the filename. This file can then be rendered in within the code of a view page without having to re-write the code. For example, in my Rails application, there were various instances where I listed the collection of cocktail recipes. Rather than repeating this code throughout my views, I created a partial containing the code that displays a collection of cocktail recipes. 

#### Cocktails List Partial: 
<script src="https://gist.github.com/chrisbaptiste83/9f2f7ffb1c09bff24ae0c7967a74f553.js"></script> 

### Locals 

When rendering partials, the locals parameter can be used to allow you to share a partial between different views.When we use locals, we need to make sure that the variables we refer to in our partial have the same names as the keys in our locals hash. Take a look at the partial for rendering a list of cocktail recipes being used multiple times on my application's profile page below.  

#### Partials In Profile Page
<script src="https://gist.github.com/chrisbaptiste83/aa8d47fc12c461b0297dcd38314e06d8.js"></script>

### A Note on Locals

When rendering the partials, the first key-value pair tells Rails the name of the partial to render ("cocktail_recipes/cocktail" and "cocktail_recipe/cocktails"). The second key-value pair specifies the locals as a Hash. That Hash's keys cocktail_recipe and cocktail_recipes here) will be created as local variables within the partial. When we use locals, we need to make sure that the variables we refer to in our partial have the same names as the keys in our locals hash. The way we use locals with a partial is similar to how we pass arguments into a method. In the locals Hash, when the cocktail_recipes: key is the argument name, the value of its argument is the value stored as cocktail_recipes.five_latest_cocktail_recipes and passed into the method. We can name the keys whatever we want. In this instance, we are calling a scope method on the value of the locals Hash. 

## Scope Methods 
Scopes are custom queries that you define inside your Rails models with the scope method. If you take a look at the code above, there are scope methods being defined on the values of the locals Hash when rendering the partials. I defined these methods in the CocktailRecipe class. Here take a look below: 
<script src="https://gist.github.com/chrisbaptiste83/d17ac164fec15f85588484f3b553aeee.js"></script> 

Scopes aren’t doing anything magical or super special. They’re just methods. In fact… You could do the same thing using class methods! However, there are design advantages to using scopes over class methods. Here’s why:
scopes result in cleaner code because of their syntax, scopes are used for exactly one thing, so you know what you get the moment you see one, and scopes aren’t mixed with other methods, so they’re easier to spot. In terms of functionality, the only difference is that scopes guarantee an ActiveRecord::Relation, and class methods don’t. This helps you avoid errors when your scope returns nothing. 

##### Check out my Github repo [here](https://github.com/chrisbaptiste83/rails-cocktail-app).


