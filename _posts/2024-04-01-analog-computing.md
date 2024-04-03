---
title: Where are the analog computer startups?
author: Jeff Kantarek
date: 2024-03-28
layout: post
mermaid: true
---
<div class="row">
  <div class="column column-70" markdown="1">
We used to live in a world with only analog computers. Purpose built machines that could take an input and give the output.  Take the [Antikythera mechanism](https://en.wikipedia.org/wiki/Antikythera_mechanism) an _ancient_ analog timekeeper on steroids. While trivial for us today this was a huge military advantage to coordinate ship movements across time and space.  Military requirements for computing [ballistic trajectories](https://en.wikipedia.org/wiki/Rangekeeper) were all analog and capable of computing "[firing solutions](https://www.reddit.com/r/explainlikeimfive/comments/y1m3ta/eli5_what_is_a_firing_solution/)."  Someone literally has to do the math and come up with a _solution_.
</div>
<div class="column column-30" markdown="1">
![](/assets/images/analog-defender.webp)
</div>
</div>
<!--more-->
The most famous analog computer is talked about so rarely but we've all been exposed to the results of it, the [Electronium](https://99percentinvisible.org/episode/player-piano/transcript/).  It's an analog computer that could actively feedback on itself and build up not just a solution but a tapestry. Where the hallucination is the feature.  You can even make your own Electronium with [ChatGPT](https://chat.openai.com/share/a217432a-0edb-4531-ac1c-0ff548305989) and [Sonic Pi](https://sonic-pi.net/)!

<iframe width="560" height="315" src="https://www.youtube.com/embed/6fdTkOK-Xlo?si=09Mjy0w4__s_ueW6" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

My favorite way to work with ChatGPT is to lean into those hallucinations.  While there are far too many AI published books spewing across amazon there's something incredible about watching an AI slowly build up a cohesive story.  I've [tried](https://chat.openai.com/share/5ce2423a-e983-4e48-b108-c2fbe8d232e0) in [fits](https://chat.openai.com/c/60ea1475-0a53-4314-9c02-7c15d1168eff) and [spurts](https://chat.openai.com/share/b9d2f103-639e-4966-aa87-c820cc363475) to help [articulate](https://docs.google.com/document/d/1Zq9AhdSeufoUzRDTRA-TdVoCW7H18ljV5zI_vGvkgK4/edit?usp=sharing) why I wish analog computing would make a real serious comeback.

<div class="row">
  <div class="column column-60" markdown="1">
We already know our current designs are rocketing towards an energy crisis and that Moore's law is reaching a fabrication limit. We need a [Sophon](https://www.amazon.com/Three-Body-Problem-Boxed-Set-Remembrance/dp/1250254493) moment, a way to build computers in more than one dimension without boiling circuits in the process.  Thankfully, the technology already exists, HP just biffed it.

</div>
<div class="column column-40" markdown="1">
![](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExbm1jdmxqbTU2MDd0NnZmMjFlOWU2YmZwMnRkaGhleTc0Z2txcmU3eiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/XQ0ULpbArqtZXbS4To/giphy-downsized.gif)
</div>
</div>

## 1970s, HP, memristors and mazes

I'm going to skip the complications of describing electronic theory and the overall [history of memristors](https://www.americanscientist.org/article/the-memristor). The TLDR of where we are is roughly: Transistors were invented in 1947 ushering in digital signals. Memristors were invented only _theoretically_ in the [70s by Leon Chua](https://www.thinkartlab.com/rodrigo/chua/Memristor_chua_article.pdf). HP built a physical device in the mid 2000s and has struggled to commercialize the technology to this day.  HP is no longer the shining beacon of tech that [it once was](https://www.techradar.com/news/computing/what-happened-to-hp-1302804). If I had to guess, someone at HP struggled to explain what memristors _could_ do and decided it was more important to scale the technology via a known consumer product (RAM/ReRAM) than try and build a whole new market.

Why should any of us care about an HP flub? Because we're already 50 years behind on analog computing that can fundamentally change how we approach problems that memristors can solve with grace. A memristor has four _very_ special properties:
1. Its resistance changes depending on how much current flows through it over time
2. The _direction_ of the current flow matters. Left to right increases resistance, right to left decreases resistance
3. A very _small_ amount of current can tell you what the device's resistance is without changing it.
4. The set resistance is not lost when the memristor loses power

<div class="row">
<div class="column column-50" markdown="1">
![](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExZ3FwZzBvNms5azF0bDNweDdvOHU5YXNxcXRuM210NTBtNHZmZnlndCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/1hMjJILpxoWpQad37L/giphy-downsized.gif)
</div>
<div class="column column-50" markdown="1">
The _most boring_ application for a memristor circuit would be a clock that you can understand how long it had been without power.  Say you had a memristor that could go from a resistance of 1 Ohm to 86400 Ohms (the number of seconds in a day).
</div>
</div>

Every second that passed would increase the value of the memristor.  8:44 AM would be the same as 31440 seconds (the number of seconds since midnight). Say the power went out at 12:33PM and came back at 1:42PM. You could _immediately_ tell that the clock was off for a little over an hour because it would have come back and show 12:33PM instead of flashing 1200.  In general this seems very boring but a staggering amount of software development is dedicated to keeping track of how much things have _changed_ with high accuracy.  

<div class="row">
<div class="column column-50" markdown="1">
Things get interesting when you build _networks_ of memristors. They have been used to build massively [parallel solutions to mazes](https://arxiv.org/pdf/1103.0021.pdf), finding the lowest energy path through a network.  What happens when you treat these networks as multi-dimensional? What happens when you have mazes within mazes and arbitrary start and end points?  You start to build something that resembles how the human brain works and stores information.
</div>
<div class="column column-50" markdown="1">
![](/assets/images/memristor-maze.png)
</div>
</div>

The way data-science and mathematics describes collections of data where each item in the collection goes off in many directions with many different values is called a tensor.

## Tensors and surface manifolds

A [tensor](https://www.grc.nasa.gov/www/k-12/Numbers/Math/documents/Tensors_TM2002211716.pdf) can be used as a way to describe a complicated path through space.  A _very_ approachable video to understand both tensors and how to write code against it is by the incredible José Valim:

<iframe width="560" height="315" src="https://www.youtube.com/embed/fPKMmJpAGWc?si=X2snjAlXn8FXiiRw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

If you're curious about playing with elixir and tensors you can quickly bootstrap your experience using [livebook](https://livebook.dev/)

Your head, and the hairs on it, are a _perfect_ example of a tensor that is multi-dimensional. First, the _shape_ of your head is the surface manifold that contains point sources. Each point vector is simply a single hair follicle.  The distribution of the follicles tells you how sparse (aka bald) your vector field is. The individual strands of hair are themselves a chain of tensors because your hair can have kinks and curls be strong or brittle across its whole length.  Lets break it down a little bit:
* **2-dimensions** - the _surface_ of your head as a complex curved and maybe even rippled space
* **point source** - pretend your head is broken up into zones only a little bigger than a follicle, each zone contains either zero (no hair) or a hair vector. There's also the possibility of a compound follicle which is a fun wrinkle.
* **n-dimension hair tensors** - each strand of hair has its own uniq set of properties to describe what it _is_.  You have different values across the length of a single strand for every attribute, color, thickness, pliability, curl etc. 

<div class="row">
<div class="column column-30" markdown="1">
![](/assets/images/hair-tensor.webp)
</div>
<div class="column column-70" markdown="1">
Bare with me for a second and lets double down on this analogy. A single strand of hair is a tensor with memory/history. Say you colored your hair, as it grew out multiple attributes, including the color, are different as time passes and your roots grow in. The length of hair that was colored still maintains the applied pigment but the root is the _original_ hair color. This slowly grows out and re-dominates the length of hair. If you pluck that single strand of hair it has a knowable history by external observation (much like a memristor). 
</div>
</div>
Now that you have a more intuitive sense of what a tensor can represent lets take ourselves back to the world of memristors.  Imagine a multi-dimensional network of memristors that represent a foundational model. The model is defined by the structure and how each piece is connected, like a single color lego set. Each memristor though has flexibility to work across a _range_ of values compared to our current models that just have a simple fixed value weight. It would be like a lego set that changes color, piece by piece, as it is built making for an individually uniq set but still conforming to the original design.

So please, someone, start working on scaling memristors for true analog _compute_. Help build frameworks to translate a trained model to an FPGA of memristors.  Help claw back the future that HP managed to mess up.

<iframe width="560" height="315" src="https://www.youtube.com/embed/p0qd2Kvj_v4?si=tEAJut_TkOahOyDa&amp;start=1000" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>