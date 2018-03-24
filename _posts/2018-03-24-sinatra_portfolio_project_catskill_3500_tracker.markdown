---
layout: post
title:      "Sinatra Portfolio Project: Catskill 3500 Tracker"
date:       2018-03-24 23:20:50 +0000
permalink:  sinatra_portfolio_project_catskill_3500_tracker
---


To complete the Sinatra section of the curriculum, I needed to make a CRUD app that tracks something. A user would be able to create, read, update, and delete information stored in a database. 

![](https://i.imgur.com/0xrhrYJ.jpg)

I browsed some Flatiron student blogs to see how they fared with their projects and came across a hidden gem called [Corneal](https://github.com/thebrianemory/corneal), which was created by a fellow Flatiron alumnus specifically "to help fellow Flatiron School students with their Sinatra assessments." It provides the skeleton of a Sinatra app with all of the necessary files and folders, and it was extrememly helpful for starting this project. Thank you Brian Emory!

I'm currently aspiring to be a member of the [Catskill 3500 Club](http://catskill-3500-club.org/) by hiking to the peaks of all 35 mountains in the catskills with elevation above 3500 feet. I was using a spreadsheet to track my progress before I came up with the idea for my Sinatra portfolio project - the Catskill 3500 Tracker. After signing in, I can see the list of peaks I've hiked, add new ones, and edit or delete them too. I can also view the peaks other users have hiked. 

I really want to make this project into a live site some point to share with friends, so I added a bit of styling. I also got carried away with adding features, such as a dropdown menu for the possible peaks. 

![](https://media.giphy.com/media/3PyvQJONLWa58U2WzP/giphy.gif)

I had to make some decisions along the way of coding this project. Could a user have multiple usernames under the same email address? I decided no, so in the User model I added requirements for usernames and emails to be unique:

```
validates :username, :presence => true, 
                     :uniqueness => true
validates :email,    :presence => true,
                     :uniqueness => true
```

I learned so much throughout the process of creating the Catskill 3500 Tracker. I'm excited to revisit the project in the future to add features and improve the code using the knoweldge I gain from the upcoming sections in the curriculum. 

