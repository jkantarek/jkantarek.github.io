---
title: In the weeds
author: Jeff Kantarek
date: 2024-03-04
layout: post
mermaid: true
---

<div class="row">
  <div class="column column-30" markdown="1">
  ![](assets/images/in-the-weeds.png)
   </div>

  <div class="column column-70" markdown="1">
I cook for fun and to feel better about failing. The _most_ satisfying meals are the big ones where everything arrives hot and on time. Then there are others where you get in the weeds and everything starts falling apart.  You have to start picking and editing what happens next and who you're likely to disappoint to get things back on track. Some software developers _live_ in the weeds, trying to get features out the door or getting pulled into on-call firefighting can be an every day problem. Getting out of the weeds requires two important steps: identifying the next worst problem, and sitting down to do the work.
</div>
</div>
<!--more-->

## What is the next thing that is going to kill me

Canadian [heart throb](https://www.youtube.com/watch?v=KaOC9danxNo) and astronaut Chris Hadfield had an [amazing interview](https://www.npr.org/transcripts/241830872) with Terry Gross in 2013 that is always on my mind. Whether it's during an on-call incident, trying to avoid a toddler meltdown, or finishing dinner:

> **What's the next thing that's going to kill me?** And it might be five seconds away ... I know that this is dangerous, but there are six things that I could do right now, all of which will help make things better. And it's worth remembering, too, there's no problem so bad that you can't make it worse.

Being calm and meticulous during an incident is the fastest way to resolution.  Identify the immediate problems, write them down, prioritize them and assign them out.  And remember, there are almost always stakeholders that are watching. They are anxious about things being broken. By providing clear, consistent communication about what is happening, as it is happening, you are helping everyone on the sidelines feel better. You are who they trust to get things back on track as soon as possible.

How do you practice being in the weeds so it doesn't feel as overwhelming? Have a plan and then push yourself. Even if that plan is for the next five minutes. Set a target and knock it out. You'll be amazed at what you can accomplish in a short burst of time. While I'm not the biggest fan of reality shows Top Chef holds a special place in my heart.  Professionals that _think_ they are at the top of their game mixing creativity and skill to create something beautiful.
<div class="row">
  <div class="column column-60" markdown="1">
<iframe width="420" height="206" src="https://www.youtube.com/embed/UqslydNbrAc?si=MD9vgWgwJn3aP-Gr" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>
<div class="column column-40" markdown="1">
My favorite part of this clip is the quote "Every move is synchronized perfectly with the next one." Going fast is more about efficiency of every move, not juggling multiple things. When you're trying to get out of the weeds don't get distracted by the things that are not _now_ problems.
</div>
</div>
Put them off to the side for future you to think about.  Getting out of the weeds is all about stopping the bleeding and getting back to a state where you're in control. After that, it's making sure the work gets _done_.

## Always be preparing

Both Chris Hadfield and Tom Colicchio came into their situations being _prepared_. Astronauts train for their entire career working upside down, off balance and spinning. Chefs spend _years_ doing prep work at every station on the line. Every day you write code you're _preparing_. The deeper you understand your work the more effective you'll be at solving problems. The more work you _finish_ the more you'll have an intuitive sense of your domain.

During my time in the [maker movement](https://en.wikipedia.org/wiki/Maker_culture), I realized that it's more important to finish _something_ than to keep trying to figure out what to do next. The idea of this is distilled (at least for me) by the [Done Manifesto by Bre Pettis](https://medium.com/@bre/the-cult-of-done-manifesto-724ca1c2ff13) and [JFDI from Chicago's Pumping Station: One](https://wiki.pumpingstationone.org/wiki/Just_Fucking_Do_It). The done manifesto is worth reading in its entirety:

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
> **Done is the engine of more.**

<div class="row">
  <div class="column column-30" markdown="1">
<a data-flickr-embed="true" href="https://www.flickr.com/photos/opacity/4012567553/in/album-72157623230988760/" title="psone--no longer kid-safe"><img src="https://live.staticflickr.com/2621/4012567553_17589d2f7d_3k.jpg" alt="psone--no longer kid-safe"/></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>
 </div>

  <div class="column column-70" markdown="1">
JFDI (Just Fucking Do It) is, surprisingly, a little more nuanced because...power tools. The other way to frame it is **Instead of complaining, fix the problem**.  Start-up culture is largely realizing that everything isn't built, won't all get built today, and might not be worth building.  If you have a straight forward, reversible change, make the change. It's almost always ok to fix a crappy piece of code if you're running into it while you're adding functionality. If you have the right testing in place making that kind of change should be easy right? What isn't ok is spending 3+ weeks in a corner fixing something that annoys just you.
</div>
</div>

## Get it done daddio

<div class="row">
  <div class="column column-50" markdown="1">
All of this _doneness_ needs to be in service of something though. While there are plenty of cases where you can be self satisfied with personal projects. If you're here because you're trying to figure out how to be a better career software developer here is my last piece of advice for getting your work done: **You are responsible for getting your code to production.**  You should feel uncomfortable when your work gets stalled out.  If you're stuck, say something, ask in a public channel so your team can help unblock you.
</div>

  <div class="column column-50" markdown="1">
  ![](/assets/images/tried-nothing.gif)
  </div>
</div>

Stuck _has_ to mean that you hit your head against a wall _at least_ three times. You should be able to come into a conversation and clearly say I am stuck with X, I tried A, B, C and they failed in specific ways.  Even better the act of explaining your problem to someone else will help you come up with ways to fix it.  If you want to really get to the heart of your understanding try and use the [Socratic method](https://openupthecloud.com/what-the-hell-is-the-socratic-method-and-why-as-a-developers-you-should-care/). It's a way to approach problems through continuous questioning to find your gaps in knowledge but it can feel painful and slow.  The slowness is worth it though because you will typically understand your problem and solution more deeply.