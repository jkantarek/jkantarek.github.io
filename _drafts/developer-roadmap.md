---
title: Developer Roadmap - Overview
author: Jeff Kantarek
date: 2024-03-04
layout: post
mermaid: true
---

Clarity of Thought - The intent of this focus area is to improve your ability to think though problems and present effective solutions that you can both invision and execute
Effectively breaking down tasks into 1 to 2 days of work. Isolating work into logical chunks/frames that make it easier to release as either dark code or behind a single feature flag. Each bullet below is an logical frame to package work (and sub-breakdowns)
Database changes
Schema changes, indexes etc
Model changes
expose a new column in a table
Add a db query
Business Logic changes (the code that transforms db data to work at the api layer aka services in our codebase)
Service interfaces
Api changes
Serializers
Gql types
Router changes
UI changes
Api adapter changes
Adding a new component
Exposing a new component in the UI
Effectively breaking down Epics into tasks
Releasable chunks of work that take about 1 week to complete where each piece is ~1-2 days to get into production
Presenting Changes as clearly as possible
Code that speaks for itself
https://thoughtbot.com/blog/sandi-metz-rules-for-developers  - Baruco 2013: Rules, by Sandi Metz
RailsConf 2016 - Get a Whiff of This by Sandi Metz
Intentional Commits
Strive to put up PRs where every commit has clear meaning and the commit order tells a story for your code rather than relying on github alphabetical order for a review. One good strategy here is trying to hold yourself to the rule that “every commit contains two files, one for the change you made and one for the test for the change that you made”
Accountability and Urgency of work
Striving to push code every day to production
Being uncomfortable with stalled work
Building strategies for unblocking yourself
Communication, Jira and automating “checking in” - the more a jira ticket shows that work is moving forward the less likely anyone will need to check in or bother you in a flow state.
Bias for Action - Every solution doesn’t have to boil the ocean, moving work forward and getting something out the door will go a long way to being an effective dev. The Cult of Done is a great short read to approach problem solving!
Managing tickets and providing clear communication
Avoiding Empty stories and using stories as a way to clearly call out what you’re building
Clear expectations from pull requests - it’s ok to say a pull request is explicitly not doing something and is expected for a follow up.
Building mental models
Abstraction layers - be able to guess and check that assumptions are correct
Using raw SQL to sanity check assumptions
Using sentry/datadog to sanity check current volume and volume growth trends
Understanding how computers work more fundamentally
Code Book
"The Mess We're In" by Joe Armstrong
Computer Science - A Guide for the Perplexed • Joe Armstrong • GOTO 2018
Be able to answer the question: Why is linux transitioning to Rust (and what are they transitioning from)?
What is the difference between OOO and Functional Programming?
Concurrency vs Parallelism
Global interpreter lock
Concurrency Optimizations and Crazy Scaling
What problem was react invented to solve?
What problem was graphql invented to solve?
What is the difference between CPUs that are multi-core vs single core with hyper-threading?
What’s the difference between CPU cache(s), Memory, and On-Disk memory
What does it mean when an application cannot fit “In-Memory”?
What is the difference between functional and OO programming languages?
What are chrome extensions capable of?
What is the difference between Fork and Spawn when it comes to multi-process/multi-threaded code?
Code Structures - Being able to distinguish between a language, a framework and the infrastructure will help you understand how to better build systems that are loosely coupled, but still contain high data integrity
MVC frameworks - what are they, what problem were they invited to solve?
Domain driven design
Hiding complexity - thin models, thin controllers, etc
https://thoughtbot.com/blog/skinny-controllers-skinny-models
https://medium.com/marmolabs/skinny-models-skinny-controllers-fat-services-e04cfe2d6ae
Encapsulation of ownership - models own db queries, serializers own data presentation, services own orchestration and data transformation
https://martinfowler.com/architecture/
Metaprograming and where be dragons - understand when to use abstraction and what to do when facing complex problems.
Logging
How does logging work from code to screen?
How do logs get from code all the way to datadog through aws?
How do log buffers work?
What can happen when you try to log a giant object?
What happens when an exception is thrown inside of a log?
What’s the difference between a log in a background job and an api request?
How do trace ids work across infrastructure?
Resources
https://www.toptal.com/python/in-depth-python-logging
https://www.crowdstrike.com/guides/python-logging/advanced-concepts/
https://docs.python.org/3/library/logging.html
Building Curiosity for code
https://www.youtube.com/@StrangeLoopConf
https://www.youtube.com/@PyConUS
Building empathy for business needs and working effectively asynchronous
ReWork Podcast (in general)
The value of being a good writer
Appetites and Budgets vs Estimations
Everything Doesn’t need to be perfect 
Tooling Expertise
The intent of this focus area is to make your tools do more thinking for you and avoid mistakes or time-sinks that slow you down as a developer.  Additionally, being able to understand and appreciate the history of each of these. Understanding why a tool was built in the first place helps you build a better baseline understanding of what kinds of abstractions are possible.
Shell
What is the shell?
What are your shell options?
https://betterprogramming.pub/fish-vs-zsh-vs-bash-reasons-why-you-need-to-switch-to-fish-4e63a66687eb
What is POSIX compliance?
What is a .rc file?
Super charging your shell
Tooling like oh-my-zsh to make your terminal hyper obvious to your dev state
Git
Rebasing vs merging
Interactive rebasing
Reflog
Git-blame
Python
Complete and explain python koans
Virtual environments
Pipfile and Pipfile.lock, Managing dependencies
Django
Knowing what django magic is and how to understand it
Demystifying Django’s Magic — Smashing Magazine
React
What problem was react invented to solve?
What is the react render loop?
How do slots work?
What does it mean to have props “fall through” components?
Javascript
Async handling and Promises
Pitfalls
Lodash vs pure javascript
How did we get to ECMAScript
API kinds
REST
GraphQL - what problem was graphql invented to solve?
GRPC
Debugging code
Prints vs debugging
Testing
TDD
E2E/synthetic tests
What is the difference between an end to end test and a synthetic test? What is the benefit of one over the other?
Docker
What is a container
What does a dockerfile do?
What does a docker compose file do?
What problem was docker invented to solve?
What are docker pitfalls
Postgres
Comfort connecting to and doing basic raw sql queries against the read replica
What problem was jsonb solving?
SQL vs NoSQL
AWS/cloud infrastructure
EC2 Instances
RDS
Regions
ECS and container registries
IAM roles
What is multi-cloud
What is the difference between a VPN and an SSH tunnel?
Monitoring and Observability
Sentry
Logs
Datadog
Personal Development - growing as a developer isn’t just about writing code, as you progress through your career you end up taking on more responsibilities and will be put in a situation where you need to explain the what and the why of something you built.  Additionally, you’ll likely be put in a situation where you will have to advocate for a solution.
Public Speaking
https://www.toastmasters.org/about/90th-anniversary/90-tips
Writing
https://ocw.mit.edu/courses/21g-225-advanced-workshop-in-writing-for-science-and-engineering-els-spring-2016/
Effective Data presentation
https://ocw.mit.edu/courses/cms-631-data-storytelling-studio-climate-change-spring-2017/
