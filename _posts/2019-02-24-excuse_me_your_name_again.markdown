---
layout: post
title:      "Excuse me your name again?"
date:       2019-02-25 02:07:30 +0000
permalink:  excuse_me_your_name_again
---


Have you ever gone to a meetup and get Introduced to someone?
 You make a mental note of the persons name and go on to have a great conversation. Ten minutes later you find yourself talking to another two people and then six more.
 ![](https://cdn.pixabay.com/photo/2015/07/08/06/54/group-835427_1280.jpg)
Soon you realize that the first contact this evening, is the one that you have the best chances of developing promising partnership with. The venue is buzzing with people mingling and you’re trying to find him, but - Oh no, you forgot his name!
:-( If only I was a computer this would not have happened. I mean that’s only until I tried making my a Rails/JavaScript application.
If I can only get the front-end part of my app to remember who is the current user. 
I finally turn to a good friend, one whom I’ve never met in person, but I’ll never forget his name: Google that is. He in turn, introduced me to localStorage.
And it’s a simple as 

Example
The snippets below accesses the current domain's local Storage object and adds a data item to it using Storage.setItem().

localStorage.setItem('key', 'value');
```
localStorage.setItem('myDog', 'Tom');
```

The syntax for reading the localStorage item is as follows:

`var dog = localStorage.getItem('myDog');`

The syntax for removing the localStorage item is as follows:

`localStorage.removeItem('myDog');`

The syntax for removing all the localStorage items is as follows:

`localStorage.clear()`;


