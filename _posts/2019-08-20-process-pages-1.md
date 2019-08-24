---
layout:     post
title:      "Day 17 of #100DaysOfCode"
series:     "Process Pages"
date:       2019-08-20 20:00:00
summary:    An overview of notes, raw documentation of each day in my #100DaysOfCode journey
categories: #100DaysOfCode
tags:
 - documentation
 - raw
---


# Intro
---------

Since I created this blog after I started the #100DaysOfCode challenge, I've been back-tracking a little bit with some of the articles. The last one however [Bonus: Account recovery hell]({% post_url 2019-08-19-working-with-windows-3 %}), was written mostly during and directly after the events described actually occurred. I realized pretty quickly that I liked that a lot more, so while I'll still be writing my original kind of articles too, I'm now starting a separate series in which I'll document every coding-related activity I do that day, whether that's research, creating/working on a FreeCodeCamp project or working on my blog since a lot happens behind the scenes with that as well. Warning: the documentation in this series will be raw (though some of it might make its way to other, more polished articles in other series at a later date).

# Adding comments to my blog? 
--------------------------------

## Why I removed my comment section originally

The theme that I forked from Github to use for this blog (Carte Noire) originally had a comment section that made use of Disqus. I thought about removing it or not, but in the end I decided to get rid of the code making the comment section possible. Mainly because I wanted to build my blog from the ground up, meaning start with the basics and add any extra functions as I go. To me this is important because it gives me very specific and relatively small projects to work on within a bigger project and I'll learn a lot more if I then research and implement the code myself, because let's be honest, the chances of me really looking at it if it's already in my forked code files are slim. 

## Why I now want to implement it again

Now that I feel like I'm getting a little more comfortable working with my new blog and I've got a couple of articles online, the thought of implementing the comment section has crossed my mind a couple of times. I have friends asking what the response to my blog has been and the truth is, I don't quite know, so I figured it's time to open up that line of communication and hope someone actually uses it.

## Why I'm not convinced about using Disqus
Now here's the issue I have with Disqus: it's a third party application and preferably I'd like to avoid those. Not only for security reasons, but because anyone who doesn't have a Disqus account can't participate in the discussion and since we web devs are so big on accessibility for everyone, that just seems kind of wrong. I want to know that anyone who wants to reply on my article can if they want to. All that to say, I'm definitely not convinced about that option and I'll be looking for one that fits my needs better.

## Doing research
I remembered from doing some quick earlier research that there were options out there without having to use a third party application, so my first thought is to look a little more specifically for those instead of the previous and more general "Jekyll blog comments" search I'd conducted. 

The first search result that comes up [Various ways to include comments on your static site](https://darekkay.com/blog/static-site-comments/) seems familiar and Google tells me I have indeed visited this page before. I open up the page and it offers a pretty extensive list of different ways to integrate commenting into a static website like mine split up into different categories. The first one are all third party applications, but I read through them quickly anyway as a plan Z, because you never know. The second category offers up self-hosting options, so I work my way through those as well, but I'm still not sure that's the direction I want to go in. 

## What I want my commenting system to look like
Reading through those two categories and its linked documentation does give me a nice indication of what I don't want my commenting system to look like, thus also giving me a clearer idea of what I DO want it to look like;

I want it to be as minimalist as possible, meaning no third party authentication (for the above mentioned security reasons and performance speed), preferably even an option for anonymous posting if the user prefers that, no tracking or ads, but at the same time I want it to be a positive environment, so the possibility to moderate/delete mean or negative comments is a must to me. While I'd very much like to receive advice or constructive criticism, I don't want a comment section filled with irrelevant or unnecessary comments either. I'm not expecting to receive an immediate influx of comments, so I don't mind the little extra work that will come with being a moderator myself. Tagging onto the positive environment, I don't need a system of upvotes or downvotes since it's not relevant to my type of blog and we all know some people just really like to downvote for no reason at all. I do need an option to be able to reply to a comment and the system displaying that hierarchy. All that said, I'd really also prefer a free option at this point, since like I previously mentioned, I'm not expecting a 100 visitors a day all commenting all of a sudden and right now I do this because I want to, not because it gains me much (besides probably wisdom from writing out all of my thoughts, or at least I hope so!)


# posting latest article in Working with Windows series
---------------------------------------------------------

I took a break from figuring out my comment section dilemma to work on getting the content of my latest blog post in the Working With windows series live. 

I write all of my content itself in Evernote for the same reason that I absolutely love  Spotify: I can use it anywhere and just continue working, switching between devices pretty seamlessly. Granted, the mobile version is somewhat limited and there's likely different and better note taking apps out there, but I'm used to it and it does what I want. Since it has a pretty straight forward text editor, it also allows me to style my articles visually the way I want them to look in my live version without having to worry about markdown qt the same time, which I'm not the best at. Good thing this blog is forcing me to get better at it, whether I want to or not. 

Now I have to admit I kind of do this the wrong way, since I usually copy my latest post, adjust my front matter and then delete the existing body to replace it with the correct one. I should probably just create an empty template post file to copy instead, which would only hold the front matter without its actual values (*Note to self: implement this fabulous idea*). 

I copy/paste my content into a new post file and make the necessary adjustment to include the markdown for the styling I want. I cheat a little bit with the styling, because for longer articles, the theme I chose gets a bit harder to read and so far I haven't figured out how to overwrite some of the styling I'd preferably like to adjust (like the font-size), so for now I just use lines under my headers to at least create some kind of structure, making reading a tad easier. I'm also still somewhat frustrated at how my rendered version seems to squish lines that should have an entire line break between them together, but again my previous efforts were fruvitless and I don't feel like getting into that right now, so I decide to let it go and come back to it at a later date. Now that my article looks decent enough on my local version, I make sure to do a commit and then push it to my remote repo to publish it live. It doesn't take long at all before I can see the changes in my blog, so I click the article to make sure and it looks good. 


# FreeCodeCamp Responsive Web Design project 1 
------------------------------------------------

## Where I left off
I managed to include most of the html to pass the tests (user stories) and finished the "header" area (full width and height of area visible before a user scrolls, I was struggling to find why the body had a margin when my stylesheet should overwrite that margin;



## What I'm doing
Decided to take another look at the margin issue since it's causing me to have overall lay-out problems ... was ready to post a screenshot on Twitter to ask for help ... glad I didn't because it turned out I put a "#" in front of my body tag in my css file (insert simultaneous eyeroll and facepalm). Glad I caught that right in time! 

![A screenshot of Dev Tools highlighting the margin issue and the problem](/assets/Margin-Issues-Resolved.png)

I keep side-tracking with this darn design and while I know ultimately this exercise is about practicising HTML and CSS, I'm pretty solid at those. Yes, I'm using it to refamiliarize myself after having focused on other areas, but I'm also trying to improve my eye for design. I just can't help it! I feel like I like how the header area looks, but I need to break it up with a different color or texture. I play around a little bit with different colors, but ultimately darker looks better in contrast to my blue gradient header than a lighter color does in my eyes. I then have some fun with the box-shadow property to give it that extra little bit of depth, creating a slightly more fluent transition from one area of my webpage to the next. 

-------------------