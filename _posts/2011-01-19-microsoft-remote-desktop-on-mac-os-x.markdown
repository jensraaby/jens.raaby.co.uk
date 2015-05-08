---
comments: true
date: 2011-01-19 15:18:07
layout: post
slug: microsoft-remote-desktop-on-mac-os-x
title: 'Microsoft Remote Desktop Client on Mac OS X: "Cannot verify the identity of
  the computer that you want to connect to"'
wordpress_id: 77
categories:
- Computing
---

Once again a little bit of tech support to fill a gap in the Google results... This time I am publishing a quick solution for an error with Microsoft's Remote Desktop Connection client for OS X. This will most likely affect you if your Windows machines are not on a corporate network (with a Domain Controller). The summary: don't leave the host name in the "Domain" field of the credentials dialogue - blank it.

<!-- more -->

If you wish to remotely connect to a Windows (in this case Windows 7 Professional) machine from your Mac, then you may come across this error:

[![The error shown when trying to connect to the Windows PC using the Mac Remote Desktop Connection](http://jens.raaby.co.uk/wp-content/uploads/2011/01/rdc-error.png)](http://jens.raaby.co.uk/wp-content/uploads/2011/01/rdc-error.png)

The description is not that helpful, especially when you know that the target machine is accessible from the Mac: "Remote Desktop Connection cannot verify the identity of the computer that you want to connect to." My first thought was to check that I could ping the Windows PC and verify that the Mac could communicate over the network. This succeeded, which left me scratching my head. I then tried changing the settings for accepting remote desktop connections on the PC itself, so that it would accept lower security connections (not really something you would want to do if the port is open to the internet.) This did not solve it either.

[![The connection dialogue box for the Mac RDP client](http://jens.raaby.co.uk/wp-content/uploads/2011/01/rdc-connect.png)](http://jens.raaby.co.uk/wp-content/uploads/2011/01/rdc-connect.png)

Normally when connecting to a Windows machine over the network, you must supply a login domain. In the case of a standalone PC, this will be the host name, often "yourname-pc" if you used the suggestion Microsoft offers. The Mac RDP client puts this in for you by default. In the example shown above, I had entered "laptop" and told the client to connect - this was the next dialogue shown. I entered my username and password and clicked 'OK'. That is when the error (eventually) popped up. I finally deduced that this seemingly unrelated error message could in fact be traced to the "Domain" field. Using the host name would be correct in this situation, however for some reason the only way I could actually connect was to **clear the field completely**.
