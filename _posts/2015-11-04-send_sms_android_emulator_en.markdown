---
layout: post
title:  "How to send SMS to Android Emulator"
date:   2015-11-04 20:13:18 -0200
categories: jekyll update
---

This is my first blog post and I will start with a very simple solution for a 
problem that a I had some time ago.

In order to send a SMS to an Android Emulator you just hate to:

* open a console/terminal
* find the portnumber in the title of the emulator
* connect via telnet to the running emulator: `telnet localhost [portnumber]`
* type this: `sms send senderPhoneNumber textmessage`

[Reference](http://stackoverflow.com/a/4325836/1107651)
