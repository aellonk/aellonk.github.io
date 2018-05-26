---
layout: post
title:      "Marco Polo "
date:       2018-05-26 01:01:47 -0400
permalink:  marco_polo
---


Sometimes learning to code feels like a game of Marco Polo. I'm swimming in a pool of methods trying to find the right one, but in this post I'm lifting the blindfold and exposing the difference between the `.find` and the `.find_by` Active Record methods. 

The [.find](http://api.rubyonrails.org/v5.2.0/classes/ActiveRecord/FinderMethods.html#method-i-find) and [.find_by_id](https://www.rubydoc.info/github/jnicklas/capybara/Capybara%2FNode%2FFinders:find_by_id) methods both search for an object in the database that matches an ID in the argument. The [.find_by](http://api.rubyonrails.org/v5.2.0/classes/ActiveRecord/FinderMethods.html#method-i-find_by) method also does the same search when the argument is ID. So in an effort to keep the code [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) and as minimal as possible, your initial coding instinct might be to use the `.find` method if you are searching by ID. **What happens if the record matching the ID isn't found?** This is where we take a look behind the scenes and shine a spotlight on the differences between these methods. 

When calling the `.find` method with the argument of an ID that isn't in the database, Active Record will raise a RecordNotFound error.  This method assumes there is definitely an object with the ID you ask for. So if it finds the object, then it returns the object, which is great! If it doesn't find it, you'll get an error, which isn't really helpful in an `if` statement to handle a case where it doesn't find the ID you asked for. For instance in a music app index, if a user searches for an artist based on their ID, they could see all the songs by that particular artist. If the artist couldn't be found, you might want to let the user know and redirect them to see all artists. Here's the code:

![](https://i.imgur.com/wSe68vV.png)

I use the `.find_by` method here because the if statement depends on its return value. It either finds the record of the artist, or it will return nil. If the artist can't be found, returning nil is what we need in order to execute the else statement. Alternatively the `.find` method would throw an error and it wouldn't reach the else statement. The `.find_by_id` method also gets the tests passing in Rails v4.2.5 but it appears to be [deprecated](https://apidock.com/rails/ActiveRecord/FinderMethods/find_by_attributes) and isn't standard practice anymore. 

Although DRY is generally a great principle to code by, sometimes lengthier, more explicit code saves the day. 

TL;DR: In the case of a music app search, `Artist.find_by(id: params[:id])` wins in comparison to `Artist.find(params[:id])` because the .findby method returns nil if it's not found, and the .find method raises an error if it's not found. 

For more information on DRY vs. WET code:

* [Codementor](https://www.codementor.io/joshuaaroke/dry-code-vs-wet-code-89xjwv11w)

For more information on the difference between these methods:
* [Stack Overflow](https://stackoverflow.com/questions/15185919/whats-the-difference-between-find-where-and-find-by-id/15185941)
* [Blog](http://duanesbrain.blogspot.com/2008/01/activerecord-find-vs-findbyid.html)
