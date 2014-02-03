---
author: admin
comments: true
date: 2011-02-07 05:41:31+00:00
layout: post
slug: macs-pngs-and-web-design
title: Macs, PNGs, and Web Design
wordpress_id: 67
categories:
- Programming
---

Note: this article is highly technical.

My dad recently got a MacBook Air, so tonight I decided to test my current website project to make sure the fonts looked okay. All my Calibri replacements looked great (Helvetica is a nice font), but I discovered a much nastier problem. For some reason, instead of an image blending into the background like I had designed it, the colors didn't match.

<!-- more -->
At first I thought I had accidentally changed the background on the live site instead of tweaking it in Firebug, but the website looked fine on my own computer. I thought there might be some extra code loaded (which was the case with an IE7 bug I fixed yesterday), but there wasn't. Since the page background was the right color, I realized there had to be something strange about the images.

I went over to the #css channel on Freenode IRC, where I learned about the existence of something called gamma correction. This is a value intended to correct the differences between CRT and LCD screens, which is embedded in the PNG image format that I used on the site. It turns out that modern web browsers ignore this value, except on Mac. Part of the reason Apple displays look so nice is that they adjust the gamma of images to make the colors brighter. In most cases this is okay, but if the system applies a different gamma correction to images and background colors, it will cause an ugly mismatch.

[This page](http://hsivonen.iki.fi/png-gamma/) has a good explanation of the problem. I found a solution on [this page](http://f6design.com/journal/2006/12/01/fixing-png-gamma/). If you're a Windows user, you'll need to download a freeware program called [TweakPNG](http://entropymine.com/jason/tweakpng/). (If you're a Mac user there is a similar program called pngcrush.) This program allows you to edit the low-level data of a PNG image. Open each affected PNG image, delete the gAMA and sRGB chunks, reupload the PNGs, and refresh the page. This should fix the problem in every browser except for some old Mac versions of Safari and Opera. For those, you're just out of luck.

Strangely enough, I did not have any gamma correction on my PNGs - the GIMP defaults to leaving it out. My problem was the sRGB chunk. The sRGB color space was created so that colors could look the same on every screen, but in my case it caused the opposite since Mac respected the sRGB specification on the image but not on the page background. Deleting this chunk put both in the same color space and made them match again. As far as I can tell, there is no way to make GIMP leave this out.

The moral of this story is either: 1. Apple is evil, 2. You should borrow a Mac and test on it, or 3. PNGs are the second leading cause of headache and facepalm in web designers (the first, of course, being Internet Explorer 6). I suspect all three are at least partially true. In any case, I hope this post might help some random web designer in the future.
