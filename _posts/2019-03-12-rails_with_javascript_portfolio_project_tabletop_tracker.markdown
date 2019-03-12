---
layout: post
title:      "Rails with JavaScript Portfolio Project: Tabletop Tracker"
date:       2019-03-12 11:35:18 -0400
permalink:  rails_with_javascript_portfolio_project_tabletop_tracker
---


I expanded upon my Rails project, Tabletop Tracker, to include dynamic features that are possible only through JavaScript and a JSON API, and I learned so much along the way.

I planned for the project kickoff meeting by answering the following: 

1. What is your plan to render an index page via JavaScript & JSON? <br> List the user’s matches, organized by game name on the Users Show page
2. What is your plan to render a show page via JavaScript & JSON? <br> Allow a user to sift through each games' matches by clicking a 'Next' button on the games show page, with the next game being fetched via AJAX and rendered through JavaScript. 
3. How will you implement rendering a has_many through relationship via JavaScript & JSON? <br> List the games’ users on the games show page (games have many users through matches) 


4. What form will you use to submit via AJAX? <br> The new game form is fetched via AJAX on the users show page with the `getNewGameFormFromRails() ` function:

![](https://i.imgur.com/cgZnbJPl.png)

Submitting the name of a new game brings the user to the new match form. This will have various fields based on the game. The form is submitted with the `submitNewMatch()` function:

![](https://i.imgur.com/khOcuEnl.png)


Then after the new match is submitted a confirmation appends to the DOM along with the match info and an option to edit or delete the match. 

**What Tabletop Tracker Does**<br>
Use Tabletop Tracker to keep a record of your wins, losses, and other attributes from tabletop games. Which character do you win most often with? What's the ideal player count for you to have a successful game? Find out the answers to these questions by analyzing your Tabletop Tracker history. 

**How I Built It**<br>
Ruby on Rails, JavaScript, and Bootstrap. I also utilize AJAX, JSON, jQuery, SQLite3, Bcrypt for password hashing, Omniauth for Facebook login authentication, and HTML5.

**Challenges I Ran Into**<br>
The API and AJAX sections of the Flatiron curriculum was tough! Before I began adding JavaScript features I needed a supplemental lesson, and Udacity delivered. Their course [Intro to Ajax](https://classroom.udacity.com/courses/ud110) really solidified my knowledge on requesting data from APIs by using jQuery AJAX functions. Even before starting at Flatiron School I had jumped around the various free tutorials online because each one has a different approach and utilizing a few of them allows for more practice. I appreciate seeing the information from another perspective.

The users show page has a sort of visual glitch problem that I haven't been able to solve. The first table header is appearing before the name of the game even though it is in the correct order in the HTML, and it is correct for the other games listed. I am using JavaScript to append the parts of the table to the DOM. This is the output:

![](https://i.imgur.com/oM9lZKlh.png)

**Stretch Goals**<br>
Next I'd like to refactor the code for more efficiency and better legibility. I also want to work on styling and focus on UX. Ideally I would like to have it finished and deployed in time for the annual [PAX Unplugged ](http://unplugged.paxsite.com/)conference so I can share it with the tabletop gaming community. 
![](https://source.unsplash.com/collection/3824435/800x450)

**More Info** <br>
[Github Repo](https://github.com/aellonk/tabletoptracker)
[Video Walkthrough](https://vimeo.com/323238200)

