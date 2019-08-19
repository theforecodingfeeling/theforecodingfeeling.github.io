---
layout:     post
title:      "Bonus: Account Recovery hell" 
series:     Working with Windows
date:       2019-08-19 17:00:00
summary:    A step by step retelling of getting started with Windows after using only Linux
categories: [Windows]
tags:
 - Microsoft
 - password
 - struggles
---

#### Author's note:
Chronologically speaking this post doesn't entirely fit this series, since these events occured AFTER the ones that will be described in part 4 (and likely 5, possibly 6), but since part 2 of this series and this post are pretty interconnected, I decided to post it out of chronological order. 

### Intro
---------
So I got myself in a little little bit of a pickle. I've been building out my Windows environment and so far it hasn't been quite as bad as I somehow thought it was going to be. Don't get me wrong, I've had some struggles adjusting, but all in all it's been a fun learning journey. Then the Great Account Recovery Hell occured, at least that's what I'm calling it. 

### The problem 
---------------
Here's the scenario: I'm writing out my previous post in which I talk about Windows' start menu being kind of stuffed when you open it for the very first time. My first thought it that it would be nice to get a before and after picture but I can't exactly undo my work. Then I remember the account I created exactly for purposes like this, so I log out of my Administrator account and try to log into the secondary account. Yeah ... turns out none of my usual passwords work and I'm scratching my head trying to remember if I made a new one for some strange reason and totally forgot about it. Deciding it ultimately doesn't matter, I do the next obvious thing and start the process of resetting my password. It says it'll send an email to the email adress I use for my Administrator account, which is fine by me. I open up a browser, go to outlook, enter the email address and then the exact same password I've been using to access my Administrator account this entire time with absolutely no issue and it gives me an error because my password is incorrect. At this point I'm huffing in frustration because I'm not having much luck and on top of that, i'm baffled. Of course my mind doesn't like the mystery of my password working in one place but not the other and needs to figure it out. So there I am, my hands on my keyboard, looking at the Google Search bar with no clue whatsoever what keywords to use or how to phrase my little question. Now I like to think my Google Search skills are pretty solid usually, but how do I explain that I can log in to my account, yet I can't? No matter what I used, it kept showing me pages to reset my password. Obviously I know how to do that since I just did it for my secondary account which led me to my little issue with my primary account. Figuring that sitting with my head in my hands isn't very productive and only making me more frustrated, I decide I might as well reset this password too. Of course that doesn't quite work out because instead of a back-up email address, my option for this one is a phone number ... that's no longer in use (insert facepalm). I click the option that states I don't have the above method(s) and it asks me a TON of questions. Let me let you in on a little secret: I haven't actually used any of my Microsoft accounts for email purposes in years and honestly only still had an account because I've only ever had Windows computers and since it kind of keeps asking you to enter a Microsoft address, inevitably it's just easier to have one. Long story short, I aced my security questions (at least I knew that part), but then it asked me about latest emails, senders and subject lines, what services I've used this account for and all I can think is "I haven't actually used it besides to log onto my computer/administrator account in ages so I don't know." At this point, this whole situation is starting to get to me, because I feel like Alice just falling deeper and deeper into that hole. I'm already assuming that Microsoft isn't going to accept my request because I didn't really fill in all that much info besides the aforementioned questions, so I'm basically stuck. 

### Finding a way to override my password
-----------------------------------------
If there's one thing I try to do when I get stuck and feeling overwhelmed, it's to take a step back and look at the core problem/goal. In my case, the core goal is to gain access to my secondary account with the issue being I don't know my password. If I can find a way to gain access to the acount despite that, I don't even need to worry about the other password issue at the moment since I only really need access to my Administrator account on my laptop, not the Microsoft services connected to the email address. I'm thinking it's time to get out my new friend Powershell, administrative tasks like this being part of its job and search for ways to reset a password of another account. 

#### Step 1: Get-LocalUser 
The first thing I need to do is get the exact name of the user account I was trying to access since it obviously won't work without that. One "Get-LocalUser" cmdlet later and a short list of accounts appears, making it easy to find the information I'm looking for. 

Now I have to actually reset the password, for which I found and tried two different methods:

#### Step 2, option 1: 

```net user <UserAccountName> < * | Password>```

This command is actually meant for Windows' command line interface (cmd.exe), but since many of those also seem to work in PowerShell, I thought I'd give it a try. There's actually 2 different ways to use this command with both achieving the same goal, just in a different way. If no one else is watching your screen and the new password doesn't necessarily need to be hidden, you can just fill in your new password as the second parameter. However, if you want this to be a little more secure, use * as the parameter instead. The user will get a prompt after entering the command and the password will be hidden by * upon entering it. Since no one really uses my computer and my secondary account doesn't need the highest form of security, I choose to just type in the password without the prompt and get confirmation the command was succesfully executed. Not entirely sure if this requires a reboot but figuring it couldn't hurt, I restart my computer. Of course when I try my new password on the secondary account, it doesn't work and that dreaded error message still pop ups.

#### Step 2, option 2: 
Powershell and variables
The second method is actually for PowerShell instead of a cmd command and requires three lines of code instead of one. 

```
$Password = Read-Host -AsSecureString

$UserAccount = Get-LocalUser -Name "name"

$UserAccount | Set-LocalUser -Password $Password
```

The first line tells PowerShell to read the string the user will enter after this line of code is executed (secured so no one can read along) and store it in a variable called "Password". 

The second line stores the name of the account we're trying to work with into a variable called "UserAccount". Insert the name found from our earlier "Get-LocalUser" cmdlet, which could be admin or any other name, mine being "thefo", the shortened version of my handle that I used to create the secondary account. 

The last line basically says to take the value put into our UserAccount variable (again, mine being "thefo") and use that account to change its information, namely the password, using the one we stored in our password variable as the value for it. 

Now that I've completed that process, I decide to reboot again, but alas ... same result as before with yet another error message saying my password is incorrect. 

### Trying a different way 
--------------------------
At this point I figure I've spent enough time trying to fix this password issue and it might be time to approach it from a different angle. The point of the whole secondary account was that it was untouched and that I could show certain aspects of building my dev environment to others after I've familiarized myself with it in my primary account (which also holds sensitive information I don't necessarily want to show people on screenshots or possible future videos since I've played around with that thought). I'm thinking of just deleting my secondary account alltogether and just creating a new one, but I really don't want to make yet another new Microsoft email address just to be able to log into my secondary account on my laptop, which is what I did in the first place and look where that got me. So I go back to my Google Search tab, left open in my browser from all of my research and see if there's a way to just create an account without that dreaded Microsoft email address when I find the miraculous "local account" option. With a big sigh of relief, I use my GUI to go to settings, because at this point I just want to get this done in the quickest and easiest possible way so I can get back to finishing my second post, which at this point is still missing that "before screenshot" that started this whole thing. I go to my account settings, navigate to other accounts, select my original secondary account and click that "remove" button without and ounce of regret. Then I set up another account, but make sure to select the option stating to use a local account, fill in my username and my new password twice and decide to restart my laptop for a third time for good measure. Third time's the charm, right? Turns out, this time it actually is and my log-in to my brand new account is succesful. Pro-tip: If you're as bad as me at remembering passwords, you might want to write them down somewhere. I made sure I did!

### Bonus: unexpected good luck
-------------------------------
While I'm celebrating, some part of me is still irked about the password for my primary account working but not working when I remember I added it to my list of email accounts on my phone (because Gmail is easy and lets you add non-Gmail accounts, granted it has definite other issues). Opening up my app, I smile when I see I did in fact add it and open up my inbox. Immediately I notice an e-mail warning about a password change. Ah ... so there's our culprit. Luckily it gives an option to reset it, which gives me no problems at all this time and instead of making me verify my identity, gives me the option to enter my new password pretty much right away. Doing just that, I decide to check if it works now by trying to log in to my email on my laptop and it accepts my new password right away! This situation made me go slightly crazy, but in the end, I got it all fixed AND I learned some new things while doing it! 

----------------