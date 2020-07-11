---
layout: post
title:      "Creating a Web Scraping CLI Gem"
date:       2019-09-15 08:30:22 -0400
permalink:  cli_data_gem_project
---

## Getting Started
For my first project, I decided to create a command line interface (CLI) gem that scrapes two websites for data and provides a user with a collection of the best weapons to have during a zombie apocalypse. I chose this topic for my project because I am a very big fanatic of firearms, zombie video games and zombie apocalypse television. I figured that I would incorporate my interests into my first project as a way to have fun during the process and push myself to learn even more. Initially, I was a bit nervous about creating a CLI gem from scratch. However, it eventually became a very fun experience and also a great demonstration on how much I've learned from the course so far. To get started on my gem, I used Avi's CLI Gem Walkthrough video. This video provided me with all of the information that I needed to start my gem and set up its environment.  

Perhaps the most important step in the early development phase of my CLI gem was brainstorming on and visualizing how I wanted a user to be able to interact with it. During this point of the process, I had to take into consideration what kind of information I wanted the gem to display to a user, what kind of options would a user have when interacting with it, and how I would want the information provided to be displayed on the terminal. After some arduous brainstorming which included me writing a step by step guide on how ideally my gem would work, I was able get started and get to coding. 

## The CLI 
Designing my CLI class was the first thing that I dove into doing. This class contain's most of the application's logic and handles the methods that are called depending on what a user inputs. As a matter of fact, a new instance of this class is what is actually created inside the bin file when this application is started, and the call method gets called to it. Take a look here: 

<script src="https://gist.github.com/chrisbaptiste83/fb3b3dc2263bb8c1c942de31f28747d3.js"></script> 

#### This is what the CLI class look like:

<script src="https://gist.github.com/chrisbaptiste83/3a1fe5bf84523247c1f2eca2e5e245bd.js"></script> 

As you can see, the make_firearms and make_melee_weapons methods get called before the welcome message and main menu prompts. These methods are responsible for scraping information from the web and creating models from the scraped data. Depending on the input that a user then enters, these models and their attributes are then displayed on the terminal. My CLI gem allows a user to choose from two categories of weapons and then displays a list of the top ten weapons for each of the categories. Upon selecting a weapon from a given category, a user can access a title and description of the selected weapon. Depending on what type of weapon selected, a user is provided with a certain type of link to an external website.  The weapons on the melee weapons category have a link to an amazon page where the selected weapon is being sold, and the weapons on the firearms page have a link to an external website with additional information on the selected firearm. The melee weapons also have a brief history descritption in addition to the regular description. After selecting a weapon and being provided with these deails, a user then has the option of selecting another one of the type of weapon they had just selected, viewing the list of the weapons from the other category, or exiting the program. 

## The Scraper Class 
The scraper class is responsible for scraping data from the two websites that I used and storing it as hashes inside a couple of arrays. I found two websites that ranked the top firearms and melee weapons to have during a zombie apocalypse and used them for the information on each of the weapon categories. Although both websites ranked the top ten weapons in each category, the manner in which they displayed the information was not the same. For example, the website that contained the melee weapons contained a paragraph with a bit of history about each melee weapon while the website that displayed the information about the firearms did not. For this reason, there was an additional attribute of history assigned to all melee weapons. Furthermore, the firearms website did not have headers on the paragraphs since the titles of the weapons that it described were provided as links included in the paragraph text.  The differences in the structure of the websites that I used to scrape the data for my gem caused the methods that I utilized in doing so to be different as well. 

<script src="https://gist.github.com/chrisbaptiste83/bde187210e81d7b679aadc1949e9f915.js"></script> 

              
When creating my scraper class, I encountered a problem when scraping melee weapons that I did not encounter when scraping firearms.The website that I used was not entirely consistent on the manner in which it displayed the information about the melee weapons. There was a weapon in this category(trench knife) that did not have an individual paragraph for its history and another paragraph for its description. Instead. the weapons description and history were on the same pararaph, which was throwing off my iteration when I was scraping each of the melee weapons' description since I was doing it based on text location on the html. In order to fix this, I had to incorporate a conditional statement in my scrape melee weapons method that would assign a specific portion of the history paragraph as the description of the trench knife melee weapon, and assign only a specific portion of the history paragraph as its history. In order to accomplish this i had to split the paragraph text that i was scraping by every period, then select a specific index range to represent the new history and another specific index range of the new array to assign as the new description of the melee weapon. I also then had to modify the iteration of description key of the melee weapons that were scraped after the trench knife to [index-1] in order to make up for the missing index on ther trench knife melee weapon. 
					

## Firearm and Melee Weapon Classes


### Firearm Class: 

<script src="https://gist.github.com/chrisbaptiste83/63738a017a870d83c99f8067288fa287.js"></script> 

### Melee Weapon Class: 

<script src="https://gist.github.com/chrisbaptiste83/6360b345b78fc84baa3057721f340478.js"></script>

        
The firearm and melee weapons classes have a class method to create a collection of objects based on the arrays of hashes that are scraped by the scraper class. Both the firearm and melee weapon classes have metaprogramming methods in their initialize methods that allow them to assign the key/value pairs of the hashes that they take in as atributes and their values. While the scraper class is responsible for scraping data from websites and storing it as hashes, the firearm and melee weapon classes create firearm and melee weapon object instances from the arrays of hashes that they take in as arguments.  

#### Check out the Github repo: https://github.com/chrisbaptiste83




