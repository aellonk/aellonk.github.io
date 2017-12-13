---
layout: post
title:      "CLI Gem to Find Adventures"
date:       2017-11-30 01:08:46 -0500
permalink:  cli_gem_to_find_adventures
---


I coded a Ruby CLI gem to find outdoor adventures in any state based on an activity. It scrapes data from [The Outbound Collective](https://www.theoutbound.com/) website. I frequent this site to find recommended hikes and I've even [posted](https://www.theoutbound.com/aellon) a few. 

At first I was overwhelmed by the CLI Data Gem project. I ended up completing the whole next section of the curriculum on SQL before going back to tackle it. After I watched Avi's [daily deal](https://www.youtube.com/watch?v=_lDExWIhYKI) gem walkthrough video and browsed the references provided, such as the [World's Best Restaurants gem](https://github.com/dannyd4315/worlds-best-restaurants-cli-gem), I felt ready to start coding. I found that I was more motivated than ever and I looked forward to working on it each day. 

I created a repository and got the file structure needed for the gem using [Bundler](http://bundler.io/man/bundle-gem.1.html). 

`bundle gem adventures`

I stubbed out the interface in my notes.md file, and then started programming from the place where the user interacts with it. The user would type `adventures` to run the executable file, which is the 'adventures' file I created in the bin directory. In this file I instantiate a CLI instance in the Adventure namespace, and call upon the call method. It looks like this:

`Adventures::CLI.new.call`

The objects encapsulate all of the logic. I started with the CLI class. This class contains all of the code that takes the user through the journey of the gem. It offers instructions and prompts, gets input, and sends the input to other classes. The other classes include the Scraper class and the Adventure class. 

The Scraper class interpolates the activity and state entered by the user, and utilizes  [Nokogiri](http://www.nokogiri.org/) to get the webpage and parse the HTML to scrape adventures.

The Adventure class contains variables and parses the detail page of the adventure to be called upon in the CLI. It also contains a method to find the user's choice of adventure, and a method to work with all of the adventures. 

The final product looks like this: 
![](https://i.imgur.com/4m9iqZAl.png)

It starts by asking which activity the user wants, then lists the activity titles and locations. The user chooses which adventure to learn more about and then it shows the details.

![](https://i.imgur.com/WhDgchbl.png)

At the end of the details, it asks the user if they would like to see another adventure.

![](https://i.imgur.com/dNl7xIzl.png)

That's it! I found Corinna's study groups really helpful for this project. The session for 'Portfolio Project Prep: Use an API for your CLI Gem Project' was a great walkthrough and since it was live I was able to ask questions and get answers on the spot. I also went to Office Hours and I learned why the initialize method arguments in the Adventure class should equal nil as a default.

`initialize(title = nil, location = nil, url = nil)` 

It is a placeholder so if the webpage doesn't contain some of that information when scraping it won't break the program. 

Problem solving is my favorite part of coding so even though I got stuck here and there throughout the project, I embraced those times. I used the recommended resources and a lot of Stack Overflow to try many possible solutions until one worked. I'm looking forward to the constructive feedback. In case you want to check out the gem on github the repo is located [here](https://github.com/aellonk/adventures), and a demo of the gem is [here](https://vimeo.com/245310033).
