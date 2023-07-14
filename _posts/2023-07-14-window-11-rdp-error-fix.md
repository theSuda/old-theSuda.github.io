---
published: true
title: A fix for Windows 11 Remote Desktop error "Your credentials did not work"
layout: post
tags: windows11 RDP remote-desktop
category: windows-tricks
author: Sudarshan Kadam
excerpt_separator: <!--more-->
---
Trying to connect a Windows 11 Pro laptop with Remote Desktop Connection, I kept getting following error:
  
_"Your credentials did not work. The credentials that were used to connect to machine name did not work. Please enter the new credentials:"_
    
## The Fix...
**Did you login with a PIN to the remote machine????**   
### Just logout and <ins>login with a password.</ins>

Here is how to user password instead of PIN (just in case): On login screen, click 'Sign-in Options' under 'I forgot my PIN', then click the second icon to switch to Password mode.  
  
**That's it. If you have enabled RDP, logging in with password should fix it.**

If it is still not fixed after this then go try the firewall settings and all that stuff from google.
  
  
  
### Rant:  
After scouring the internet and trying many things like firewall settings, changing passwords, using different account, disabling and re-enabling RDP and many other things, I had given up. Until I came across a comment on this issue reported on Microsoft forums [here](https://answers.microsoft.com/en-us/windows/forum/all/remote-desktop-problem/853f56e5-69fb-4bfd-bfc6-41e2a5cc006d).
  
It's funny how a million articles/listicles for fixing this issue had no mention of this fix that actually works. I love coming across solutions in seemingly casual comment at forum threads that are basically abandoned by the OP and the forum 'experts'. Kudos to random user named 'Robin Smith4' who has just 1 post on MS forums that happened to fix my problem.
