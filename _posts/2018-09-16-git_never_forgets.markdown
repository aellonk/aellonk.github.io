---
layout: post
title:      "Git Never Forgets "
date:       2018-09-16 20:47:10 +0000
permalink:  git_never_forgets
---


Git has changed my life as a developer. I won't go into all of the [benefits of Git](https://www.atlassian.com/git/tutorials/why-git) right now because you probably already know that version control is a lifesaver. I use Git almost every single day but I generally only work with the basic commands: 

```
git add .
git commit -m "Here's a commit message"
git push origin master
```

After working on a project for about an hour today, I realized that I accidentally tried pushing very large image files to my repository. I wasn't able to push my changes to Github because of the size so I reverted back to old commits before I added those big files. I used the command `git reset --hard HEAD~2` a couple of times to go back 4 commits, and didn't realize that this would effectively lose all of my updates to the files that I worked on for an hour. 

![](https://media.giphy.com/media/VS95jHa4UCOe4/giphy.gif)

Then panic started to set in. I just lost precious weekend time and would need to do it all over again! But I decided that doing it all over again was a last resort. What if this was a more dire situation, for instance if there was a tight deadline and I didn't have the time to start over? I needed to figure out how to solve this problem using Git, so I would know how to do it again in the future if I ever needed to. 

With some detective googling, I found that while Git may make you think it's deleting a commit like how I reset it before, it never forgets the history (thankfully). I came across [this Stack Overflow post](https://stackoverflow.com/questions/5788037/recover-from-git-reset-hard) and learned that the command `git reflog show` provides a list of the history including commits and resets. Reflog is short for reference log. From there I selected the "deleted" commit in my timeline that I wanted to go back to with the command `git reset HEAD@{5}`. Abracodeabra, I got my updates back!

Click [here](https://www.atlassian.com/git/tutorials/rewriting-history/git-reflog) for more information on git reflog.

Click [here](https://www.atlassian.com/git/tutorials/undoing-changes/git-reset) for more information on git reset.

