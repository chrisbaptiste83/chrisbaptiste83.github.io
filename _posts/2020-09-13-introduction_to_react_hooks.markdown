---
layout: post
title:      "Introduction To React Hooks"
date:       2020-09-13 19:41:52 +0000
permalink:  introduction_to_react_hooks
---


#### Prior to React 16.8, the only way for components to have and use state is to make them class components. However, this is currently no longer the case thanks to the addition of Hooks to React. The greatest thing about the addition of React Hooks is the fact that they are completely opt in, 100% backwards compatible, and available immediately. This means that they can be implemented into any React code without breaking changes. Furthermore, Hooks provide a more direct API to concepts most React developers already know (props, state, context, and lifecycle) rather than replace their existing knowledge. Let's take a look at an example of React Hooks in action. 

#### What is a Hook? A Hook is a special function that lets you “hook into” React features. For example, useState is a Hook that lets you add React state to function components. A commonly used Hook is the useState Hook. Let's take a look at the example below. First, we must import the useState Hook from React.

<script src="https://gist.github.com/chrisbaptiste83/9275fef584ab0eb4a15d6cfad9b08059.js"></script> 

#### Inside of a function component, one cannot reference "this" the same manner in which one can reference it inside of a class component. Instead, the useState React Hook can be called directly inside of our function component.  

<script src="https://gist.github.com/chrisbaptiste83/b0aa3adf4397b94c862991342e283034.js"></script> 

#### useState is a new way to use the exact same capabilities that this.state provides in a class. Normally, variables “disappear” when the function exits but state variables are preserved by React. useState always only takes the initial state as its argument. Unlike with classes, the initial state does not have to be an object. It can be set to a string or a number depending on the data type that a user is using.  

<script src="https://gist.github.com/chrisbaptiste83/1214be49e886330fec46b5a7c3a322b7.js"></script> 

#### This is what the full implementation of the useState Hook being used. setCount is called whenever the state is updated.


