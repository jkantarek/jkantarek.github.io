---
title: Le gâteau de l'abstraction
author: Jeff Kantarek
date: 2024-03-12
layout: post
mermaid: true
---

<div class="row">
  <div class="column column-70" markdown="1">
Are you the kind of developer that feels perpetually lost in a codebase? Do you struggle to figure out where and how to make changes? Is every day like cutting into a 100 layer surprise cake where only madness spills out? You're missing out on abstraction layers. Little slices of comfort that you can stand on and pretend only _one_ problem exists. Building confidence your abstractions will help you better reason through your code and the systems you interact with. 
</div>
<div class="column column-30" markdown="1">
![](/assets/images/funfetti-computer-chips.webp)
</div>
</div>

<!--more-->

## Building and Rebuilding your senses through data

<div class="row">
  <div class="column column-60" markdown="1">
  <iframe src="https://www.npr.org/player/embed/134195812/134195976" width="100%" height="206" frameborder="0" scrolling="no" title="NPR embedded audio player"></iframe>
  </div>
  <div class="column column-40" markdown="1">
   Grant Achatz is a world class chef at Alinea in Chicago.  In 2007 he was treated for tongue cancer and **lost all sense of taste**. He had to rebuild his sense of taste from zero!! In 2011 he talked with [Terry Gross](https://www.npr.org/transcripts/134195812)
  </div>
</div>

> I started from zero and the first thing back was sweet. So my palate developed just as a newborn, but I was 32 years old. So I could understand how flavors were coming back and how they synergized together.

Imagine losing all your footing for how you approach problems. You can feel completely blind and disoriented. It's critical to have anchors that you can rebuild from. I tend to lean on investigating what is in the database to understand the truth of a codebase.  There are so many small details you can rebuild to understand what _must be happening_ in the code because the database tells you so.

Take the time to build habits to query the database _directly_ instead of relying on a prod console. If you know how to query something in your ORM it is absolutely worth the time to understand the abstraction layer that was built between your code and the actual database you're working in. If you're a sucker for the terminal and using Postgres [pgcli](https://www.pgcli.com/) is a fantastic tool ([mycli](https://www.mycli.net/) for mysql).

## ORM to SQL

<div class="row">
  <div class="column column-60" markdown="1">
If you're trying to figure out how to write raw SQL there are two main tools that I'd recommend. Your ORM will almost always have an `explain` function. In ActiveRecord (built into Rails) you simply tack on a `.explain` to the end of your query function.  Rails 7.1 [exposed even more powerful options](https://www.bigbinary.com/blog/rails-7-1-adds-options-to-activerecord-relation-explain) to help you go from Ruby to raw SQL. [Django](https://docs.djangoproject.com/en/5.0/topics/db/optimization/) has a very similar `QuerySet.explain()` method.  ChatGPT is _incredibly_ good at building and re-writing complex queries.  Having confidence to use _data_ to prove what is happening is great for both digging into a codebase but also as a way to manage scope. 
</div>
  <div class="column column-40" markdown="1">
![](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNHVod3p1cXVqMTV4OWMxZ3JpdHZvbmc0YnV4cGw5MWI4bXBmN3Q1MiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/XyItwQi03YC8IGeX7O/giphy-downsized.gif)
</div>
</div>

If you imagine a specific edge case, query the database to understand the _magnitude_ of that problem. Developers love to play "what if" for big scary edge cases. If the surface area is zero for your case, build in an exception and _move on_ it is not a case that matters for your business!  If there are less than 1% of total cases, backfill the data _then_ add the exception. If there are over 100 it's likely you need to talk to product because the missed a persona!

## Simple to say, hard to do

Lets look at an example (and pretend we have this data in the database). Say we have a `people` table with a `full_name` column that is an open ended string input with zero validation. We want to **start sending emails that are addressed to just that user's `first_name`.** Should be really simple right? How many people put in `Mr.` or `Dr.` or `Sir`? do we even know if we _can_ decompose these strings?
```sql
SELECT
  COUNT(*) AS total_records,
  MIN(len) AS min_spaces,
  MAX(len) AS max_spaces,
  AVG(len) AS avg_spaces,
  PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY len) AS percentile_95th_spaces
FROM
  (SELECT
     LENGTH(full_name) - LENGTH(REPLACE(full_name, ' ', '')) AS len
   FROM
     people) AS subquery;
```

| total_records | min_spaces | max_spaces | avg_spaces | percentile_95th_spaces |
| ------------- | ---------- | ---------- | ---------- | ---------------------- |
| 1000          | 0          | 4          | 1.75       | 3                      |

As a first pass this lets us know that there's **some kind of problem.**  Now we need to understand **how big is it?**

```sql
SELECT
  space_count,
  COUNT(*) AS records_count,
  MIN(full_name) AS sample_record
FROM (
  SELECT
    full_name,
    LENGTH(full_name) - LENGTH(REPLACE(full_name, ' ', '')) AS space_count
  FROM
    people
  WHERE
    LENGTH(full_name) - LENGTH(REPLACE(full_name, ' ', '')) BETWEEN 0 AND 4
) AS subquery
GROUP BY
  space_count
ORDER BY
  space_count;
```

| space_count | records_count | sample_record                 |
| ----------- | ------------- | ----------------------------- |
| 0           | 50            | Massimo                       |
| 1           | 800           | Grant Achatz                  |
| 2           | 60            | Magnus Nilsson Fäviken        |
| 3           | 88            | Albert Adrià El Bulli         |
| 4           | 2             | Charles Michel Marie Le Fevre |

<div class="row">
  <div class="column column-40" markdown="1">
![](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExN29wZjU5eGpsbWdzeDg2cWloN3d5NzdpYzlmcm84dnE3MXQ2cGhodSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/5L2okTiupVRxC/giphy-downsized.gif)
</div>
  <div class="column column-60" markdown="1">
Armed with this information you quickly realize that splitting names is going to be a painful long term problem, your first implementation for emails will _probably_ be ok but you should dig into this data for more cases!  You also now have specific tests cases to power your implementation if you must.  As an IC or a manager this is data that I actively look at to understand how painful a refactor is going to be for myself or my team. Getting ahead of these kinds of problems avoids thrash from even happening because you're meeting your data where it already is!
</div>
</div>

