---
title: Logic dumpsters and monolithic classes.
metaDescription:
date: 2022-01-19T19:23:00.000Z
author: Marcus Engstrom
summary: Logic dumpsters and monolithic classes, if you're a dev you've probaly all seen them.
tags:
  - coding
  - learning
  - architecture
  - software principles
---
The last few days has had me really looking hard at our codebase.  It's structured as an n-tier application but is in someways like a monolithic app, certainly monolthic classes. The general architecure approach is Presentation Layer/API Layer -> BLL -> DAL.  

We have gotten lost somewhere along the way from our original path.

What has happened over time is that our generic BLL classes (aka 'Cores') have become logic dumpsters.  

Need to create a new user related function? Throw it in the UserCore! 

Instead of taking a moment to think whether that's a good approach and if it is better suited in a more focused smaller class.

After time we've let the code creep past thousands of lines of code in some of these monolithic classes.  Nothing to be proud of obviously.  Not only do these classes cause constant circular dependency issues as we try to cram yet another dependency in there but they're a nightmare to code review. They're also a nightmare to maintain.

Due to the size of the core classes the integration and unit tests classes are just as horrific.  As you can probably tell this has all sorts of code smell.

This has made me revisit software design principles and how to properly architect an application.  The things we learned in school but when we hit the work place we quickly realized you're not building a green field project but instead maintaining a monster application that has loads of legacy code.

So the goal is to apply SOLID principles to whatever I write, whether it's a new method or modifying an existing one. 

Convincing the team to do dedicated tickets to just reducing tech debt is always a struggle, so why not do a little gardening? As a developer I had the pleasure to work with said - "Whenever you step into a garden you do a little weeding and tyding up, maybe water some plants!  Basically you want to leave the garden a bit better than how you found it."

So what I've decided to do is take a gardening approach with these monoltih logic dumpsters. By doing a piecemeal approach we can tackle it bit by bit. Extract a method or two here and there into smaller more focused classes that only has a single responsibility! 

I know that refactor hell is eagerly awaiting my arrival but I step into it with the eagerness to transform and improve the code base and will always keep the following quote in mind: 

“Every software module should have only one reason to change.” - Robert Martin  

Do you have similar stories to share?  Have you been able to stick with SOLID or any other software principles?  Feel free to drop me a DM through the contact form or DM me on [Twitter](https://twitter.com/MC_Engstrom).

Take care and see ya next time.

