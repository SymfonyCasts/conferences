# Migrating to Symfony one route at a time (Steve Winter)

***TIP
Symfony Live London 2019 presentation by [Steve Winter](https://connect.symfony.com/api/alternates/cf2ab1c3-8038-406b-a1cc-527adf534fb9).
***

## Talk Abstract

We recently acquired a new client and a new project. Unfortunately this was built in a fairly old version of a framework we're not so familiar with.

There were several bugs to fix and plenty of new features the client wanted 'yesterday'! 

Initially we attempted to build these using the existing codebase, but very quickly began running into dependency hell.

Our next attempt was to work through the migration pathway of that framework, but every time we tried to move forward something else seemed to go wrong, and with no tests that was pretty scary!

The client didn't have the budget for a complete rebuild so we began by building all new features in Symfony then as other functionality needed work moving that across as well.

In this session we'll look at the challenges we faced and how we resolved them to allow us to leave the legacy application doing what it does but still being able to work with current packages and methodologies for new development.

