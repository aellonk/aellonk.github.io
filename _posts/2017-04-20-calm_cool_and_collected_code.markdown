---
layout: post
title:  "Calm, Cool, & Collected Code"
date:   2017-04-20 01:30:27 +0000
---

Recently I have been learning Nested Arrays, Boolean Enumerables, and Search Enumerables in the Ruby Tic Tac Toe section. 

Arrays are like the [Marie Kondo](https://www.google.com/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=marie+kondo) of the code world. They organize data and make a collection of information easily accessible. Nested arrays are arrays within arrays, and accessing them is really straightforward. In my Tic Tac Toe lab, I used nested arrays to list all of the possible win combinations according to their index in the board. If I wanted to access the third index of the second win combination, I would just call `WIN_COMBINATIONS[1][2]`, in which the `[1]` refers to the second nested array (`[3,4,5]`) and the `[2]` refers to the third index in that array. 

![](http://i.imgur.com/o630HLJm.png)

We can also sort and search the collections using Boolean and Search Enumerables. Boolean enumerators such as `all?`,  `none?`, `include?`, and `any?` iterate over each item in an array and return a true or false value based on what is in the array. For instance, to check if the Tic Tac Toe board is full, I have the following method:

![](http://i.imgur.com/uI2BXMgl.png)

The `none?` enumerator checks each index of the board for an empty spot, and will cause the `full?(board)` method to return `true` if it is full, or `false` if there is still at least one open spot on the board. Search enumerators including `select`, `detect`, and `reject` look into an array and pick out any matching elements. For the `won?(board)` method I used `detect` to find and return a winning combination:

![](http://i.imgur.com/pGmhdiBl.png)

Learn.co breaks up the lessons so that I coded a two-player CLI version of Tic Tac Toe in Ruby in these separate chunks. When I got to the method where players actually take turns, I couldn't figure out which way the final pieces fit together. The "O" player would never get to take a turn if I defined character = "X"  in the `turn` method. I also originally called the `turn` method 9 times within the `play` method, which isn't necessary because the `until` loop will do that on its own. 

After trying many potential solutions, I realized interpolation could help the `turn` method so that it could automatically tell whether player "X" or "O" is taking a turn, and it worked like a charm:

![](http://i.imgur.com/m86VLqFl.png)

I defined `current_player(board)` as 

![](http://i.imgur.com/9FuPAehm.png)

The biggest lesson of all so far is that I need to be cool with my code. Make it almost effortless and don't overthink it. Keep it simple!

![](http://68.media.tumblr.com/0604becebe9f68c9c916c573b1a55d37/tumblr_inline_msdfl0bMJC1qz4rgp.gif)





