---
author: admin
comments: false
date: 2011-06-08 22:53:27+00:00
layout: page
slug: portfolio
title: Portfolio
wordpress_id: 73
---

These are my most notable programming and web design projects.


## Web Design


I've been designing websites for as long as I've been programming. I had my first paid website project at age seven, when my mom needed a site for her church group. I made a number of personal websites over the years, but didn't do my first serious project until the 2009-2010 school year, when I redesigned my high school's website. That summer I started looking for more volunteer web design work to build my experience, and in December 2010 I started on a paid project for the first time since age seven.

I do most of my coding by hand in (X)HTML, CSS, and JavaScript (often using the jQuery library). I use Wordpress as a CMS (I start from scratch with the blank Starkers theme), or when something simpler is needed, I just use PHP or server-side includes to include a common header and footer on each static page.



### [Soul Rest Ministries](http://limiero.com/soulrest)


[![](http://limiero.com/michael/files/2011/06/soulrestthumb.png)](http://limiero.com/soulrest)_December 2010 - April 2011_

The most difficult part of creating this Wordpress-based site (other than settling on a design) was figuring out how to handle the menus. The menu on the homepage and the first-level menu on the other pages is a standard Wordpress menu set to depth 0 (only showing the top-level pages). The submenu was more difficult, requiring me to write some custom PHP code, a function that Wordpress calls a "menu walker" which turns the menu object into HTML code. Other notable features are the animation on the home page (powered by jQuery), the ability for the client to change the images on the home page and in the header (which can be different for each page), and some CSS3 (shadows and rounded corners).



### [michael.limiero.com](http://michael.limiero.com)


[![](http://limiero.com/michael/files/2011/06/limierothumb.png)](http://michael.limiero.com)_August 2010_

This is a fairly simple Wordpress blog. The most difficult bit of CSS was the sticky footer, which sticks to the bottom of the screen when the page is shorter than one screen, or to the bottom of the page when it is longer. There is also some CSS3 (shadows and rounded corners) to give the simple design a bit more depth.



### [Stockdale High School](http://michael.limiero.com/stockdale)


[![](http://limiero.com/michael/files/2011/06/stockdalethumb.png)](http://michael.limiero.com/stockdale)_September 2009 - May 2010_

This site was a real challenge since the school district's servers didn't support any server-side languages or any method of uploading except through Microsoft FrontPage. I eventually decided to hand-code everything in HTML and CSS, using FrontPage to handle the includes and to upload the pages. The biggest challenge was sorting through the information on the old site, figuring out how to organize it more logically, and cleaning up the code on each page to integrate it into the new design. I used HTML Tidy and the regular expressions engines in Notepad++ and jEdit to handle most of the cleanup.

I had to get creative with JavaScript to compensate for the lack of PHP. The calendar on the front page uses AJAX to scrape a list of events (in table format) from another page and present them one month at a time. The list page has some more JavaScript to show only events within a certain time period. The slideshow uses jQuery animation and gets the list of images from an array (in a separate file to prevent accidentally editing the important code). Clicking on the slideshow will pause it. The "Rules and Regulations" and "Other Information" pages use AJAX to load the short info pages in-place, without a browser refresh. There is also some JavaScript on the faculty list page to make the list easier to navigate.

After the calendar, I'm most proud of the compatibility of this site. It works perfectly in all versions of IE from 6.0 up and in standards-compliant browsers (Firefox, Chrome, Safari, Opera), and degrades gracefully in IE 5.0 and 5.5, remaining perfectly usable. The slideshow becomes a static image, the calendar disappears, and the AJAX code falls back to normal links. Even in text-based browsers, the menu is properly formatted as a hierarchical list.

Sadly, the district (not the school) decided this year to begin a switch to Edline. My site remains up but the event list has been taken down, leaving the calendar non-functional. I have a [partial mirror](http://michael.limiero.com/stockdale/) demonstrating these two pages.

[Slideshow and calendar (mirror)](http://michael.limiero.com/stockdale/)
[Event list (mirror)](http://michael.limiero.com/stockdale/news/activitiesschedule.htm)
(Today's date is set to December 5, 2009 on the mirrored pages for demonstration purposes.)
[Faculty list](http://stockdale.kernhigh.org/staff/facultylist.htm)
[Rules and Regulations - AJAX loading](http://stockdale.kernhigh.org/info/rules.htm)
