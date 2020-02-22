---
comments: true
date: 2012-05-21 10:30:07
template: post
draft: false
slug: master-your-computer-learn-to-automate-tedium
title: 'Master your computer: Learn to automate tedium'
wordpress_id: 382
category: Computing
description: "If you use a computer for anything repetitive then you owe it to yourself to learn how to automate your tasks."
---

If you use a computer for anything repetitive (_read: time-wasting_) then you owe it to yourself to learn how to automate your tasks.

If you never seen or used a command line interface, it looks like some kind of ugly window into a part of your computer that really isn't that appealing. Admittedly the "terminal" or "command prompt" is a remnant of the era when communicating with a computer involved typing on a [teleprinter](http://en.wikipedia.org/wiki/Teleprinter). Notwithstanding the arcane history of this breed of human-computer-interaction, the command line interface available on almost every personal computer (even smartphones over a network connection) yields great power to the user.

You might wonder what one would use this sort of interface for in [insert current year here]. You can't use it for viewing a full webpage with images and video; the mouse is suddenly less useful than one would expect; and there is absolutely no onscreen help or indication of what to do next.

If you know at least what is possible, then the command line is your potential army of slaves.

Here's a small example. I had a problem after upgrading the gallery application I use, which meant that a lot of identical files were missing from a folder on the web server. The boring, time-wasting approach would be to manually copy the missing file to each of the subfolders (there were 42 of them) with lots of RSI-inducing copy-and-paste actions. The alternative, more fun and automatic way to do this is to use a command line.

You can approach this sort of problem with the tools which the operating system provides.  Practically all you need to know is covered by the [Command Line Crashcourse](http://learncodethehardway.org/cli/book/).

In my example problem, I didn't know the exact permutation of commands for achieving my desired result. Enter the programmers' swiss-army-knife - the scripting language. Pretty much every programmer or computer geek will know at least one of these languages, most commonly Ruby, Python or Perl.

The main problem to solve is getting a list of all the folders which need to contain the file which is missing. My scripting language of choice has a nice function Dir.glob() which will find any file/folder path matching some pattern. In my case, I just wanted every folder (not file) under the current one. This is fairly simple to achieve in Ruby: Dir.glob("**/"). To the uninitiated, this will look rather meaningless. What is 'glob'? What do all those asterisks do? Fortunately, the internet makes it easy to lookup such things. Once you know a few building blocks of the language, and where to look and what to search for, it takes a couple of minutes of searching to find out that my entire problem can be solved with one line of code.
After launching Ruby on the command line (in the folder that I want to deal with):


> Dir.glob("**/").each { |subdir| `cp .htaccess #{subdir}` }


That was certainly a lot shorter than changing folder and typing Cmd-V 42 times. The command takes all the subdirectories, then for each 'subdir' calls the system copy utility 'cp' with that directory as a target for my file '.htaccess'. I am not expecting that command to look appealing to the average computer user, but it is not beyond any computer user's ability to learn simple tricks like this. If you have a lot of this sort of tedium to deal with on a weekly basis then I would certainly recommend looking into learning how to use the command line and maybe a scripting language.
