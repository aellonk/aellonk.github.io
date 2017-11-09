---
layout: post
title:      "Reflect & Review"
date:       2017-11-09 11:13:39 -0500
permalink:  reflect_and_review
---


I just finished creating a Tic-Tac-Toe with AI game, and I'm really excited about it! A few months ago I built a simple 2-player version while in the Intro to Ruby section of the curriculum, and that felt like such a feat at the time. I looked back at my code to use some of my methods in this current iteration. I found that I've made a lot of progress in my growth as a Ruby developer. My recent code is more efficient and simplified. For instance, instead of `@board = [" "," "," "," "," "," "," "," "," "]` I can simplify and reduce the likelihood of human error by setting the board equal to `Array.new(9, " ")`. Building the game this time around wasn't as tough as I thought it would be, and I even ended up enjoying it. I had the most fun building the AI and CLI. The strategy for the computer player looks like this: 

![](https://i.imgur.com/rhk5bM6.png)

It checks if a certain position would be a valid move, meaning that the spot is not already occupied. First it tries to go for the middle spot, then the corners, then as a last resort it goes for the outer middle spots. I tested this strategy in the CLI by making the computer play itself 100 times and report the wins. 

![](https://i.imgur.com/6Ug3LLM.png)

This method invokes the game.play method which will return "won" if any game has been won.

![](https://i.imgur.com/jB02kOQ.png)

The results have been a draw between the computer vs. computer, after playing 100 times repeatedly, so the middle > corners > leftovers strategy works. 

Although not required for the project, I added some functionality for the user. After testing the gameplay over and over, I found that I really wanted the option to exit the program at any time. So I added that into the code and put the directions in the start of the game.

![](https://i.imgur.com/enUMwFp.png)

I also included a visual reference of the possible positions the player could choose from.   

![](https://i.imgur.com/CJiBfnq.png)

I was eager to work on this project each day, because it's an interactive product of my code that I could share with the world. This is the first time as a developer I will have my code reviewed, so it feels like a milestone. While I taught myself coding for a year before starting at the Flatiron School, I was missing out on mentorship. I am really looking forward to the constructive feedback I'll receive on this project, as well as the projects ahead. 
