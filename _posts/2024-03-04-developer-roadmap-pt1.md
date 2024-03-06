---
title: Be a Farfalle Developer
author: Jeff Kantarek
date: 2024-03-04
layout: post
mermaid: true
---

<div class="row">
  <div class="column" markdown="1" style="flex:40%">
  ![](assets/images/farfalle-developer.webp)
   </div>

  <div class="column" markdown="1" style="flex:60%">
Do you find yourself writing code that needs to exist _everywhere_ before you write a test or have confidence that it is working? Are you the kind of developer that does print development or needs to have a UI to see your work in action? It's important to recognize that practice is forcing you to think about _multiple_ domains and edge cases all at the same time.  Your code change becomes a new strand of spaghetti in a code base that is already full of lots of spaghetti. Instead be a [Farfalle](https://en.wikipedia.org/wiki/Farfalle) developer. Write code that is compact and clear. It has clear inputs and outputs with a protected piece of logic in the middle.
</div>
</div>

There is one habit that I've found really re-enforces this thought process. **Every git commit should contain two files; one for your change, and one for the tests for your change.** This will force you to learn a few things:

1. **Your Code Tells a story** - Every commit message matters, `typo` `linter` etc are _not_ valid anymore. You will learn some solid Git fundimentals eg rebasing, re-ordering commits, patching etc.
2. **Your Code is Well Tested** - You'll naturally TDD because of the second requirement and actually _think_ about what is the relevant test for the specific file you're working in.  If your code is too hard to test _it is in the wrong place._
3. **Your Code is Mise en Place** The actual goal, your code is [set up, in place and in order.](https://www.escoffier.edu/blog/culinary-arts/what-is-mise-en-place-and-why-is-it-so-important-to-chefs/)

Yes, getting this right can feel painful _at first._  But building habits and muscle memory will stick with you _far_ longer than reading this post.  All of this work is in service of one thing: Developing Clarity of Thought

## Developing Clarity of Thought

Clarity of thought as a software developer, is understanding what and where you're building in a given moment. You are able to clearly articulate how your code ripples through the system you're building. How you present that code to others is equally clear. The best way to start is take the time to break your tasks or features or whatever into 1 to 2 days of work.

<div class="row">
  <div class="column" markdown="1" style="flex:30%">
And I don't mean 1 to 2 days to get a PR up for someone to approve. **1 to 2 days _to production_**. If you can't break your work down that granularly, you likely don't understand a fundamental part of what you're building or how it fits in the system. Here's roughly the framework I use when breaking down work:
  </div>

  <div class="column" markdown="1" style="flex:70%">
![](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExYmxrZTR6ZzZ5OHBmbmRhejJuNmxobm42eGUyNXlibm85YnozdHJ4NSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/yv1ggi3Cbase05a8iS/giphy-downsized.gif)
  </div>
</div>

* **3rd Party API** - do I need to build or update an API client to get the data I need. This includes building any relevant mocks/fixtures to use for later testing.
* **Database Changes** - Adding new tables and/or columns to the database. Most devs want to package this with other work but end up burning time with deployment issues where app code is disjointed in a meaningful way from the database. Do yourself a favor and just deploy these separately. It will force you to build your migrations _safely_ since you won't have app code to fall back on. See [pg_ha_migrations](https://github.com/braintree/pg_ha_migrations) if you're in the ruby world. But really these patterns are common for anyone working with a database and an ORM.
* **Batch/Async Work** - Batch and processing is usually fundimentally different than normal 1-off interactions. They deserve their own time and space!
* **Model Changes** - Exposing your new column or table in your ORM or adding a new/uniq query to a model. Adding in relevant fixtures/datacases. This does _not_ include adding business logic to a model file, that is [Fat Model territory](https://medium.com/marmolabs/skinny-models-skinny-controllers-fat-services-e04cfe2d6ae).
* **Business Logic Changes** - The code that combines together multiple queries from the model layer and defines a public interface for your new shiny piece of data.
* **API Changes** - These are the changes that start to make your work useable by other parts of the system. This should include graphQL types/interfaces, API serializers, protobuf definitions, router layers whatever gets your data into and out of the system.
* **UI Changes** - Using and potentially editing your new data in the frontend.


## An Example

<div class="row">
  <div class="column" markdown="1" style="flex:30%">
![](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOWRncDM1NDcydXpqMnV4ODNyYmhxYXZxZ2ZneTBjMDFmYTdtOThteCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/vvzMdSygQejBIejeRO/giphy.gif)

</div>
<div class="column" markdown="1" style="flex:70%">
Lets use this structure to build out a feature like **Populate work histories to our members table from the linkedin api**. Assuming there are _no existing_ LinkedIn clients that's a fair bit of work! I would separate this out into _four_ separate buckets of work.
</div>
</div>

1. Gather requirements for what the api provides and figure out exactly what data we care about including in our system. Understand what should happen when someone does not have a profile _at all_.
2. Build the backend data model changes and expose it via API
3. Build the frontend experience
4. Build the LinkedIn integration

The order here matters. Deciding on the contract between the backend and LinkedIn data _first_ means that you'll have clear compatibility between the two systems. Understanding the frontend failure cases will expose what UX will need to be supported on the frontend. Your integration becomes a hydration _tool_ that could be swapped out for some other service in the future (if you wanted to but [YAGNI](https://martinfowler.com/bliki/Yagni.html). You avoid painting yourself into a corner because your backend model is the source of truth _not_ LinkedIn.  Additionally, once the backend work is done the rest can be done in parallel. There's an overkill version where the _API contract_ is the only blocking work but that is likely _too abstract_ to be effective and is micro-managment.

<div class="row">
  <div class="column" markdown="1" style="flex:70%">
Lets combine these two strategies to really explain what is happening through a series of git commits. I like to structure my commits as `"[<TICKET_ID>] SomeClassName <add/expose/remove/updated> <logical change>"`. This structure makes it immediately clear to anyone looking through the commit history the team that is responsible for the file change and what _exactly_ was changed. The _why_ should be part of your PR. There's a whole separate topic of "Lore Managment" that I'll save for the future. The TLDR is git hygene is more useful than you realize in a startup.
</div>

<div class="column" markdown="1" style="flex:30%">
![](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExYjY5djgweWJ0bnh4NnIwemRhanp1cTgxcnVzaDV6djcwdGlrdWxtZyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/7Eipor01ypMm3LeG4v/giphy-downsized.gif)
</div>
</div>

```
[1] professions_schema.json add schema for data contract validation
[2] db professions add table
[2] Professions::Model add model
[2] Professions::PublicInterface add CRUD operations
[2] Professions::RestAPI expose Professions::PublicInterface with schema validation
[3] /members/:id/profile add Professions view UX
[3] /members/:id/profile add Professions Edit/Create UX
[3] /members/:id/profile add Professions Delete UX
[4] LinkedIn::Client add
[4] Professions::ExternalHydrate::LinkedIn add normalize linkedin data into professions table
[4] Professions::ExternalHydrate::Async add job to hydrate data based on config
[4] Cron::Manager update Professions::ExternalHydrate::Async run daily 
```

What is optimal about this structure is the relevant commits are _individually releaseable._  Each chunk should be easy to review. If something in the middle becomes complicated you have the option to stop! Now you can put the complicated work on a new branch, release what you have and focus on the complexity while still showing that you're getting your work done.

## .zshrc Snippits

I have these shell snippts to make rebasing and working with commits _way_ easier. I would encourage you to actually understand what each line is doing and why they are useful.

![](/assets/images/commits%20in%20action.gif)

<script src="https://gist.github.com/jkantarek/d9ff8632e4c381d504415b7e3625c693.js"></script>