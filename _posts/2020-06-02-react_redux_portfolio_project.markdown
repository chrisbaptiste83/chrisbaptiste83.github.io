---
layout: post
title:      "Adding Thunk Middleware To My React/Redux Application "
date:       2020-06-02 09:22:07 -0400
permalink:  react_redux_portfolio_project
---

## My React/Redux Project: Zombie Apocalypse Tactical Packages 
Today I finished my React/ Redux portfolio project. As the last portfolio project lesson put it, I earned every gym badge, defeated every boss, and wrestled with all of my inner demons to make it up to this point. For my project, I created an application that will prepare anyone for the zombie apocalypse. The name of my React/Redux application is Zombie Apocalypse Tactical Packages. For my first portfolio project, I created a CLI gem that scraped a couple of websites for the best firearms and melee weapons for surviving a zombie apocalypse. I decided that I wanted to incorporate the same theme into my final project not only because Im a zombie video game fanatic myself, but also as a manner to gauge my progress as a software developer from the start of the program up until where I currently stand.

### User Interaction and Application Features 

I created an application that will let users view, browse, and upload a collection of the best tactical packages for surviving a zombie apocalypse. In my application, a tactical package consists of a primary weapon, a secondary weapon, lethal weapon, and a tactical item. Users can browse through other users' uploaded tactical packages and explore the collections of different types of weapons or tactical items that they have uploaded as part of their desired zombie apocalypse tactical packages. A user can upload and share their favorite tactical packages by clicking on any of the links to create a package. Once a users click on any of the links to create a tactical package, they are redirected to a form to create a tactical package which has input fields for the package title, a description, and the name of its creator. Once users fill out this form, they are redirected to another page where they can add each of the tactical packages' weapons and tactical item individually. Once every component of the tactical package is added onto a newly created one, users are redirected to the tactical packages index page, where they can select the newly created weapon and be taken to its show page. If users change their mind half way through creating a new tactical package and wish to delete it, they are able to since a delete button is rendered under the tactical package's name and details on the page where the rest of its components are added on to it. Users can browse through tactical packages by their title in the tactical packages index page. A search bar is provided, in which users can type in a keyword to search in the titles of any of the uploaded tactical packages. Users can also click on any of the weapon categories in the navigation bar and browse through the collections of every type of weapon and tactical item that has been uploaded, by category.  
  
## What is Thunk? 
With Thunk, we can incorporate asynchronous code in with our Redux actions. This allows us to continue keeping our components relatively simple and more focused on presentation.
## Applying Thunk Middleware 
#### Implementing Thunk into React/Redux App:
<script src="https://gist.github.com/chrisbaptiste83/da820a92e2fee0169c5dde8e6aaeac32.js"></script> 

#### Actions: 
<script src="https://gist.github.com/chrisbaptiste83/30e93a3c5d65e0af01eebb9553b2722a.js"></script> 

#### Reducer: 
<script src="https://gist.github.com/chrisbaptiste83/699e1dfa4f9d8b0b93d9648c1db9c7f5.js"></script>

