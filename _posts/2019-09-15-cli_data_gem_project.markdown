---
layout: post
title:      "CLI Data Gem Project"
date:       2019-09-15 08:30:22 -0400
permalink:  cli_data_gem_project
---


#For my first project, I decided to create a CLI Gem that scrapes two websites for data and provides a user with a collection of the best weapons to have during a zombie apocalypse. I chose this topic for my project because I am a very big fanatic of firearms, zombie video games and zombie television. Initially, I was a bit nervous about creating a CLI gem from scratch. However, it eventually became a very fun experience and also a great demonstration on how much I"ve learned from the course so far. To get started on my gem, I used Avi's CLI Gem Walkthrough video. This video provided me with all of the information that i needed to start my gem and set up its environment.
 
 My CLI gem allows a user to choose from two categories of weapons and then displays a list of the top ten weapons for each of the categories. Upon selecting a weapon from a given category, a user can access a title and description of the selected weapon. Depending on what type of weapon selected, a user is provided with a certain type of link to an external website.  The weapons on the melee weapons category have a link to an amazon page where the selected weapon is being sold, and the weapons on the firearms page have a link to an external website with additional information on the selected firearm. The melee weapons also have a brief history descritption in addition to the regular description. After selecting a weapon and being provided with these deails, a user then has the option of selecting another one of the type of weapon they had just selected, viewing the list of the weapons from the other category, or exiting the program. 
My CLi gem consists of a cli class, a melee weapon class,  a firearm class, and a scraper class.  The scraper class is responsible for scraping data from the two websites that I used and storing it as hashes inside a couple of arrays. The firearm and melee weapons classes have a class method to create a collection of objects based on the arrays of hashes that are scraped by the scraper class. Both the firearm and melee weapon classes have metaprogramming methods in their initialize methods that allow them to assign the key/value pairs of the hashes that they take in as atributes and their values. While the scraper class is responsible for scraping data from websites and storing it as hashes, the firearm and melee weapon classes create firearm and melee weapon object instances from the arrays of hashes that they take in as arguments. The cli class then is ressponsible for displaying the attributes of the created firearm or melee weapon objects to the user after selecting a certain weapon. 
I found two websites that ranked the top firearms and melee weapons to have during a zombie apocalypse and used them for the information on each of the weapon categories. Although both websites ranked the top ten weapons in each category, the manner in which they displayed the information was not the same. For example, the website that contained the melee weapons contained a paragraph with a bit of history about each melee weapon while the website that displayed the information about the firearms did not. For this reason, there was an additional attribute of history assigned to all melee weapons. Furthermore, the firearms website did not have headers on the paragraphs since the titles of the weapons that it described were provided as links included in the paragraph text.  The differences in the structure of the websites that I used to scrape the data for my gem caused the methods that I utilized in doing so to be different as well. 
One major issue that I experienced while constructing my gem dealt with my scraper class, specifically with the method in the scraper class that I used to scrape the information about the melee weapons. This was because the website that I used was not entirely consistent on the manner in which it displayed the information about the melee weapons. There was a weapon in this category(trench knife) that did not have an individual paragraph for its history and another paragraph for its description. Instead. the weapons description and history were on the same pararaph, which was throwing off my iteration when I was scraping each of the melee weapons' description since I was doing it based on text location on the html. In order to fix this, I had to incorporate a conditional statement in my scrape melee weapons method that would assign a specific portion of the history paragraph as the description of the trench knife melee weapon, and assign only a specific portion of the history paragraph as its history. In order to accomplish this i had to split the paragraph text that i was scraping by every period, then select a specific index range to represent the new history and another specific index range of the new array to assign as the new description of the melee weapon. I also then had to modify the iteration of description key of the melee weapons that were scraped after the trench knife to [index-1] in order to make up for the missing index on ther trench knife melee weapon. 
