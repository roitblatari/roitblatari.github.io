---
layout: post
title:      "My First Gem Project"
date:       2017-10-10 02:58:49 +0000
permalink:  my_first_gem_project
---



Starting my first gem was quite a challenge for me. With endless topics to choose from, I was at a loss as to where to start from. I decided to work on a weather program, which will give the user the current weather conditions upon request.

![](https://images.unsplash.com/photo-1463694775559-eea25626346b?dpr=1&auto=compress,format&fit=crop&w=2550&h=&q=80&cs=tinysrgb&crop=)

At first, I wasn’t sure if I should start the program from a user’s perspective, which would mean that I’m working my way from outside into the program. Or would it be a better choice to work from inside  towards the outside?
As I set about from inside-out, I hit my first obstacle. Being already familiar with how to scrape a website given that all content can be found on a single webpage. However, in this case my results would vary based on any given U.S. zip code, which I could not find on a single webpage. I had to figure out how to achieve my goal.

![](https://i.imgur.com/TMGaVqc.png)

Analyzing how the website “weather.com" works, I realized that on the homepage, upon using the search bar for a specific zip code, the resulting webpage displays the given zip code on its url. 

![](https://i.imgur.com/dy3iSmw.png)

Now, by replacing only the zip code part of the url with any other given zip code, I will get valid results! Which means, that on my gem project, I’m able to use the current url by hard-coding it up-to the point where the zip code is displayed, then append user’s input (zip code). 
Score, I reached a milestone!!
