---
comments: true
date: 2011-03-30 13:42:27
template: post
draft: false
slug: adopting-new-web-technologies-the-html5-boilerplate
title: Adopting new web technologies - The HTML5 Boilerplate
wordpress_id: 128
category: Web
description: "Let's face it, all this talk of HTML5 and CSS3 is getting a bit tiring now."
---

Let's face it, all this talk of HTML5 and CSS3 is getting a bit tiring now. In every activity there are always the people who prefer to discuss the equipment or technology more than the actual activity itself. I've noticed this in particular with photography and cycling, two of my main hobbies. With photography, people often get the impression that buying a better camera will mean you take better photos. What makes a photo good is not the camera that takes it, but the person who composes and takes the photograph. I always cringe when I hear something along the lines of "you must have a really good camera" when I'm showing someone a photo I've taken. Of course I'm not showing you photos from a 1 mega pixel camera, but it was me who took the photo, not the camera. I've even had some good results with my 2 mega pixel phone camera.

In a similar vein, what matters to most users in web design is the design and usability rather than the technology that underpins them. A lot of designers out there are far more comfortable in Dreamweaver or Flash and as a result we have a lot of websites which seem outdated from a technology perspective. On the other hand, a lot of developers' sites use newer technology very well but don't appeal aesthetically.

I would put myself in both the technology and design camps, but being a compsci student means I will have to talk a bit about the technology side first.<!-- more -->

I admit that some of my sites are still using outdated technology (but no tables for layout :)). But it's about time I updated some of the code to make use of newer techniques. It's quite interesting looking at some of the work I did 10 years ago and thinking about how trends have changed. Back in 2002 I started using PHP to make parts of websites dynamic, with lots of server-side includes for things like web statistics and navigation bars, but looking back it seems a little over the top to keep using those techniques. I've recently adopted the [HTML5 Boilerplate](http://html5boilerplate.com) as a basis for a lot of experimenting. It is a little 'overkill' for a small site, but with the recent 1.0 version there is now a very handy [Ant](http://ant.apache.org/) build script which does a few nice things to improve your output.

Primarily, all your CSS and JavaScript files are combined and _minified_, reducing download size. The files are given a simple version-based naming convention, so each time you build a new file name is generated. This is particularly important if you use the server configuration files that are provided, as they change how visitors' browsers cache files.

A further nicety is the HTML reset and baseline styles. This has come into fashion in the last few years, with files like [Eric Meyer's reset](http://meyerweb.com/eric/tools/css/reset/) popping up all over the place. By forcing the developer to define their own styles for every element they use, the result tends to be more platform independent.

The major advantage of the build script for updating an older website is the image compressor. All the files within the site are optimally compressed to save loading time and page weight. I've significantly streamlined the [raaby.co.uk landing page](http://raaby.co.uk) using this method. This page is based almost entirely on images and could do with a bit of a refresh, but adopting the boiler plate system has made a big improvement. Now the YSlow speed measuring tool gives an A-rating, although it wasn't too bad before.

Even if you don't want to use the HTML5 boilerplate code for your site, I highly recommend trying out the build script. I will hopefully be able to improve my workflow (which is in a bit of a mess thanks to my Windows/Mac transition) using Ant to publish files to FTP and additionally integrate with my SVN/Git repositories.

While updating sites that work perfectly fine may seem like overkill, it is certainly useful to practice using the latest technologies and try approaching the same designs with a more up to date perspective on how to build things. I will try to make time for updating other sites to use these new technologies over the coming months. I would like to update the design of this blog to use my own design, but there isn't enough time for everything. Perhaps I should start looking at WordPress templating, although a couple of projects which might be a good [base](https://github.com/sams/Thematic-html5boilerplate) [already](http://en.blog.wordpress.com/2010/12/10/new-theme-toolbox/) [exist](https://github.com/zencoder/html5-boilerplate-for-wordpress).
