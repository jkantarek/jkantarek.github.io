---
title: Urgent Urgency
author: Jeff Kantarek
date: 2024-03-04
layout: post
mermaid: true
---

### Make it easy to always be done with _something_

A huge part of my life is wrapped up in the [maker movement](https://en.wikipedia.org/wiki/Maker_culture) from the late 2000s.  One of the most important things I realized is that it's more important to finish _something_ than to keep trying to figure out what to do next. The idea of this is distilled (at least for me) by the [Done Manifesto by Bre Pettis](https://medium.com/@bre/the-cult-of-done-manifesto-724ca1c2ff13) and [JFDI from Chicago's Pumping Station: One](https://wiki.pumpingstationone.org/wiki/Just_Fucking_Do_It). The done manifesto is worth reading in its entirety:

> **The Cult of Done Manifesto**
> 
> There are three states of being. Not knowing, action and completion.
> 
> Accept that everything is a draft. It helps to get it done.
> 
> There is no editing stage.
> 
> Pretending you know what you’re doing is almost the same as knowing what you are doing, so just accept that you know what you’re doing even if you don’t and do it.
> 
> Banish procrastination. If you wait more than a week to get an idea done, abandon it.
> 
> The point of being done is not to finish but to get other things done.
> 
> Once you’re done you can throw it away.
> 
> Laugh at perfection. It’s boring and keeps you from being done.
> 
> People without dirty hands are wrong. Doing something makes you right.
> 
> Failure counts as done. So do mistakes.
> 
> Destruction is a variant of done.
> 
> If you have an idea and publish it on the internet, that counts as a ghost of done.
> 
> Done is the engine of more.

<div class="row">
  <div class="column" markdown="1" style="flex:30%">
<a data-flickr-embed="true" href="https://www.flickr.com/photos/opacity/4012567553/in/album-72157623230988760/" title="psone--no longer kid-safe"><img src="https://live.staticflickr.com/2621/4012567553_17589d2f7d_3k.jpg" alt="psone--no longer kid-safe"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>
 </div>

  <div class="column" markdown="1" style="flex:70%">
JFDI (Just Fucking Do It) is, surprisingly, a little more nuanced because...power tools. The other way to frame it is "Instead of complaining, fix the problem."  Start-up culture is largely realizing that everything isn't built, won't all get built today, and might not be worth building.  If you have a straight forward, reversible change, make the change. It's almost always ok to fix a crappy piece of code if you're running into it while you're adding functionality. If you have the right testing in place making that kind of change should be easy right? What isn't ok is spending 3+ weeks in a corner fixing something that annoys just you.
</div>
</div>

**You are responsible for getting your code to production.** If you're stuck, say something, ask in a public channel so your team can help unblock you. You should feel uncomfortable when your work gets stalled out.  The whole idea of this is typically talked about as **Urgency**.  Some organizations use manufactured urgency to try and increase productivity, deadlines, demands of all nighters ([🧠 need sleep](https://www.npr.org/2024/02/26/1233900923/charan-ranganath-biden-memory-what-we-remember)), etc.  Having your own sense of urgency is important.  If you're able to be clear with shaping out your work, when you reasonably expect each piece to be done it's clear and obvious for everyone around you what is going on _without having to check in_. It also provides a fantastic tool of pushing back on scope creep. Smaller code changes are easier to review, approve and merge and will typically carry less risk. 

## Sandi Metz is my hero
Sandi Metz has so much amazing content on writing high quality code. I'll leave you with two of my favorites.

Small sensible "rules" to write better code:
<iframe width="560" height="315" src="https://www.youtube.com/embed/npOGOmkxuio?si=VbnBRV3IeabiA09a" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Code smells and refactoring:
<iframe width="560" height="315" src="https://www.youtube.com/embed/PJjHfa5yxlU?si=q9v7r_G0BXEyIfhE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>