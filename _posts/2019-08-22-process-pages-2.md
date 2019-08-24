---
layout:     post
title:      "Day 18 of #100DaysOfCode"
series:     "Process Pages"
date:       2019-08-23 21:00:00
summary:    An overview of notes and raw documentation of day 18 in my #100DaysOfCode journey
categories: #100DaysOfCode
tags:
 - documentation
 - raw
---

## Intro
-----

After taking two days off from the 100DaysOfCode challenge for personal reasons, I'm ready to get back to it! 

## FreeCodeCamp Responsive Web Project 1 (Tribute Page)
-----

### Pre-reflection
I've been working on this project for way too long, the danger of being a perfectionist. I've been playing around with some CSS effects to make it look a little better, but it's time to let go of the idea it has to look perfect and finish this project to move on to the next one!

### Tasks left to do

   * Finish writing tribute info section content  
   * Insert external link (id="tribute-link, target="_blank")   


### Process 

-> *Write tribute info section*
   * Since this is basically a list of facts, using an unordered list seems to make the most sense, but the bullets don't work with my lay-out.
   * To remove bullets from a list:   ``` [CSS] list-style-type: none  ```
   * Put margin on list items to create space between each item for better readability.
   * List items appear to be off-center, adding a border reveals that the list itself has an added padding to the left (natural element styling).
   * Remove borders again and set padding of list itself to 0 to counteract text appearing off-center; [ADD PICTURE]
   * Change title font, size and add margin to top and bottom for better readability
   * Add margin to bottom of tribute info section 

-> *Save progress in local repository with git commit (in PowerShell, what else?)*

-> *Insert external link*
   * Create a new div that will function as container for the link section
   * Insert span to hold text 
   * Insert link itself
   * Create span element and style it to become a small circle in the middle to separate the tribute info and the link section underneath
   * Adjust margin of tribute info section to have bigger margin on bottom for more clear separation of both sections
   * Adjust bottom margin of link section to make it smaller
   * Check if link works and opens in new tab - OK

-> *Save progress again in local repository with new git commit* 

-> *Insert footer area*
(Technically, this one isn't necessary to pass the FreeCodeCamp user stories, but adding a 'signature' is always nice)
   * Insert div to hold signature
   * Insert span element to hold text part of signature
   * Insert image within link tag (img = logo, link to github repo) 
   * Adjust font-family, font-size and margin of span element
   * Adjust height/width of avatar element for better readability
   * Add margin to bottom of avatar 
   * Check if link works and opens in new tab - OK

-> *Save progress again in local repository with new git commit*

-> *Create new repository on GitHub to hold all FCC projects, initiated with README.md that will be updated with a short reflection of each project* (this step was totally done out of order since I knew there was still some steps I wanted to do after this, but doing that last commit made me realize I didn't have a remote repository set up yet.) 

-> *Fix some of the tags used in index.html to be more semantic*
(Again, not necessary for the FFC requirements, but good practice and the point of doing these projects for me right now is to re-familiarize myself with HTML and CSS after focusing on other aspects of coding and to build good habits like these)
   * Replace unnecessary div with attribute id="main" with actual main tag
   * Move section with id="visible-before-scroll" to above main tag
   * Replace section tag with id="visible-before-scroll" with header tag instead
   * Move main closing tag to before footer area
   * Delete unnecessary section tag with id="visible-after-scroll", adjust CSS id attribute to "main" instead
   * Change href in "Learn more" arrow icon link to reflect that adjustment 
   * Check if changes made in tags didn't result in unintended visual changes - OK

-> *Add comments to indicate each of the three sections in index.html and delete unnecessary blank lines/tabs for better readability*

(In case you didn't notice from how this post is organized in sections, subsections and bullet points to symbolize some kind of structure, my mind appreciates organization, to the extreme sometimes. I'm very much pro-comments. I use them as labels at the start of each bigger 'part' of the page - and sometimes smaller ones if there is a lot of code. This way I can easily see what each part of the code does or at a quick glance, giving me a nice overview. I personally need this type of divide in code for readability purposes. Think of it like a mental table of contents ... I don't have to remember each line of code as long as I know generally where to look.)

-> *Add CDN link in another attempt to see if it works this time ... alas, still nothing -- About to remove link when I notice there is no closing tag for the script ... insert closing tag and voila, problem fixed, hallelujah!* (I struggled with this problem before and it took me ages so not sure if it was the same issue then ... oh well, **note to self: check closing tags!**)
   * Run the test, the first result is 8/10
   * Fix the missing caption issue, which I had commented out because it looked unnecessary in my design, but unfortunately necessary to pass the FCC tests
   * Fill in the missing id="tribute-link" attribute I forgot with my external link
   * Run the test again: 10/10!

-> Decide to add another subsection to the footer containing social media links (because a little marketing doesn't hurt)
   * Visit icomoon.io and generate new font with old icon (arrow) and the three new ones for social media
   * Unzip the folder with the new files, copy necessary files and paste in the correct folder, replacing the old font files. 
   * Check if previously implemented arrow icon still displays with new files - OK
   * Insert div (id="footer-links") that will function as container for the icons and handles underneath
   * Set display for above div to flex
   * Insert div (class="link-containers") inside footer-links div
   * Insert link tag for with Twitter as href value inside first link-container div
   * Insert icon tag inside link tag and add class "social-media-icons" for later styling
   * Insert span element as child of link-container/sibling of link tag  (class="social-media-handles")
   * Copy code for link-container, link, icon and span elements and paste twice
   * Adjust href value, icon class used to insert the correct icon and handle to reflect Instagram and GitHub Pages blog
   * Replace old CSS code for Icomoon icons with updated code imported from styles.css file in extracted folder
   * Set display for .link-containers to flex, but with flex-direction column
   * Set width of #footer-links to 100% and justify-content: space-evenly 
   * Add text-align: center to .link-containers 
   * Style icons to have a slight 3D effect
   * Add bottom margin to #footer-links div
   * Test if all 3 links work - OK
   * Test responsiveness - OK

-> *responsiveness touch-ups:*
   * Change px to em where possible in CSS (mostly font-size and margin)
   * Test responsiveness with Dev Tools - looking better now



## Dev Journal 
-----

### To do
   * Create template file for new posts
   * Insert day 17 raw documentation content into post
   * Insert markdown to reflect styling in original (Evernote) file
   * Push changes to remote repo to go live

### Notes
   * Fix mistake in latest post's name, leading to it appearing twice on the live site
   * Delete old file on GitHub itself to correct this unintended error;

-----