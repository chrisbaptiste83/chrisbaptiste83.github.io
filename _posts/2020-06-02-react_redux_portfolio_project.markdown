---
layout: post
title:      "Adding Thunk Middleware To A React/Redux Application "
date:       2020-06-02 09:22:07 -0400
permalink:  react_redux_portfolio_project
---

## My React/Redux Project: Zombie Apocalypse Tactical Packages 
Today I finished my React/ Redux portfolio project. As the last portfolio project lesson put it, I earned every gym badge, defeated every boss, and wrestled with all of my inner demons to make it up to this point. For my project, I created an application that will prepare anyone for the zombie apocalypse. The name of my React/Redux application is Zombie Apocalypse Tactical Packages. For my first portfolio project, I created a CLI gem that scraped a couple of websites for the best firearms and melee weapons for surviving a zombie apocalypse. I decided that I wanted to incorporate the same theme into my final project not only because Im a zombie video game fanatic myself, but also as a manner to gauge my progress as a software developer from the start of the program up until where I currently stand.

## User Interaction and Application Features 

I created an application that will let users view, browse, and upload a collection of the best tactical packages for surviving a zombie apocalypse. In my application, a tactical package consists of a primary weapon, a secondary weapon, lethal weapon, and a tactical item. Users can browse through other users' uploaded tactical packages and explore the collections of different types of weapons or tactical items that they have uploaded as part of their desired zombie apocalypse tactical packages. Users can upload and share their favorite tactical packages by clicking on any of the links to create a package. Once a user clicks on any of the links to create a tactical package, they are redirected to a form to create a tactical package which has input fields for the package title, a description, and the name of its creator. Once users fill out this form, they are redirected to another page where they can add each of the tactical packages' weapons and tactical item individually. Once every component of the tactical package is added onto a newly created one, users are redirected to the tactical packages index page, where they can select the newly created weapon and be taken to its show page. If users change their mind half way through creating a new tactical package and wish to delete it, they are able to since a delete button is rendered under the tactical package's name and details on the page where the rest of its components are added on to it. Users can browse through tactical packages by their title in the tactical packages index page. A search bar is provided, in which users can type in a keyword to search in the titles of any of the uploaded tactical packages. Users can also click on any of the weapon categories in the navigation bar and browse through the collections of every type of weapon and tactical item that has been uploaded, by category.  
  
## What is Thunk? 
With Redux, we can focus more on presentation in our React components, and use actions and reducers to handle the logic of organizing data. This allows us to continue keeping our components relatively simple and more focused on presentation.The data that is handled by my application is actually being fetched by my React/Redux front-end from the Rails API in the back-end. However, due to the asynchronous manner in which fetch requests work, we can run into certain complications when incorporating fetch requests into our Redux actions. For instance, the code in a specific action that is dispatched to make a fetch request to the back-end will run in its entirety before the promise (with data) that is being returned is resolved, which then becomes an issue. This is where Thunk comes into play. Thunk is a package that works in conjunction with Redux and handles asynchronous calls when working with Redux. In my application, Thunk is what allows an action to be dispatched saying that data is being loaded, then to make the actual request to the API, and then to dispatch another action with the response data that is returned. 

## Using Redux-Thunk Middleware 
#### Implementing Thunk into React/Redux App: 

In order to use Thunk, one must first install the npm package by running the command (on the terminal): npm install --save redux-thunk. The middleware is then incorporated into the application when the store is initialized. Take a look here: 

<script src="https://gist.github.com/chrisbaptiste83/da820a92e2fee0169c5dde8e6aaeac32.js"></script>  

Notice that we imported in a new function, applyMiddleware(), from react-redux, along with thunk from the redux-thunk package and pass in applyMiddleware(thunk) as a second argument to createStore. Here, we are telling our store to use Thunk middleware.Thunk will then allow us to return a function inside of our action creator. This function receives the store's dispatch function as its argument. With that, we can dispatch multiple actions from inside that returned function. Take a look of all of it in action (no pun intended) in the code below:

#### Actions: 

<script src="https://gist.github.com/chrisbaptiste83/30e93a3c5d65e0af01eebb9553b2722a.js"></script> 

#### Reducer: 

<script src="https://gist.github.com/chrisbaptiste83/699e1dfa4f9d8b0b93d9648c1db9c7f5.js"></script> 

##### Check out my guthub repo [here](http://github.com/chrisbaptiste83/react-app).

