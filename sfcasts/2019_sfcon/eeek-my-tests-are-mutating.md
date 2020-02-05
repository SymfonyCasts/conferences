# Eeek, my tests are mutating! (Lander Vanderstraeten)

***TIP
SymfonyCon 2019 Amsterdam presentation by [Lander Vanderstraeten](https://connect.symfony.com/api/alternates/12a431a4-414d-4f78-8ccf-db51f8cada55).


Writing tests is nice, but how are you sure that your tests cover all use cases? Code coverage can give false positive metrics. A new way of working that goes by the name of mutation testing has gained a lot of popularity lately. This talk will explain you what it is, how you can integrate it and contains a demo over the basics of mutation testing with infection and phpspec.
***

Hello. Good morning everyone. My name is Lander Vanderstraten. It's an unpronounceable name for who is not Flemish or Dutch. I'm, I'm currently a PHP developer at PHPro. I'm working for one of the biggest online gambling casinos. I'm also a maintainer of Grunt PHP, which is a really nice, nice task runner. It's very useful for people who would like to run, for example, coding styles or unit tests before you hit commit. I also have strong interests in the domain driven design, CQRS, event sourcing, and micro service. But before I start, I would like to ask you free quiz questions.

## Tests will have bugs

Who thinks, unit tests are a waste of time. Oh no, no. It's still early. But you can get out. Who always writes unit tests. Please, some more hands. Okay. You guys are awesome. It's important that your unit tests are always up to date and like I said, you can use very nice tools like Grunt PHP to make sure that every developer runs their unit test before every hit commit. Are there people who already know what mutation testing is or use? Okay. I see some, some hands over here. Well, eh, this still is more of an introduction, but I still that you guys will learn something today. All right. We are mostly all developers over here. And what we do is recreate software. We are aware that we write bugs all the time. Nobody writes bug free code. So smart developers, as we all are, we write unit tests and these tests are code. So your tests will have bugs. Tests are a good tool to verify your code. But what does verify your test?

## Code coverage is a start

Like Sebastian said that this morning, a code coverage. It's great. It's a good start. Most developers try to reach up the 100% percentage. It's the same but 100% code coverage. But are you rethinking that your application is now 100% bug free? No, sorry, it's not good. Code coverage is just a measurement of how many lines that are touched during your test suite. So still it can give a good score with useless tests for developers who are writing these tests to get up until that's 100% code coverage. So this is what good coverage looks like in real life. All the tests passed. Every letter here is inside the letter box, but it's just at the wrong place.

## Mutation testing

So how can we now detect, well bla mutation testing. So I will start by explaining a bit more but reading this definition. Mutation testing is a technique to evaluate the quality of your tests by programmatically mutating and making a small series of modification to the code with the goal that your tests no longer pass. Oh, this is a really nice show on discovery channel. How do they do it? Well, let me explain this with a basic example. If books are crimes and your tests are the police mutations are fake crimes to let people see that the police is doing their job. So a bit more technically is to assess the quality of a given test. Mutants are executed against input test to see if seeded faults can be detected.

Wow. All this terminology, mutation, mutants, WTF? So each mutated version is called a mutant and a mutated program with failing tests is a killed mutant. And that's what we actually want to achieve as I said in the definition. A mutated program with passed tests is an escape mutant. There is a modification been done on this, on the code, but still the tests are passed and that's not what you want. So let's measure all these things. Test suites are measured by the percentage of the mutant that they killed and new tests can be designed to kill these additional mutants. So with mutation testing, it's another metric. Than code coverage, it's called a mutation score indicator and it's ideal to integrate this in your CI environment. For example, you can say that we have a threshold percentage of the score indication that we want. And when we add new code, developers add new code, they used Grunt PHP to have these tests running before they git commit. You can check that the threshold is reached, for example, up to 100% that all these mutants are killed every time.

How does it modify? Well based on a list of mutators.

An example is that this is a basic function foo bar, which has an integer and outputs an integer. And for example, we increment this number. Well during our tests with mutation tests or mutation testing framework, it will change it to the increment operator to a decrement operator and check if all the tests will fail or one of the tests will fail. So this is good. Another example, for example, we try to see if the object foo is nullable. Maybe you have written a bad test and it's not nullable. This is a small modification it has been on during these infection or a mutation test suite. 

## Timings

Now what about timings as Sebastian this morning explained code coverage significantly increases during runtime when you apply your code coverage during your unit tests, especially in big project, we can add a mutation framework on top of it, but the timing will increase exponentially since we have this huge list of mutators, for example, the increment decrement, or nullable, or an equal to, not equals to, all these changes, they run the unit test suite every time over and over again. And this takes a huge time.

## Demo example

So enough with the talk, let's go right up to the demo. Good. This is all working. Before I start, I would like to show you a this demonstration project uses PHPSpec instead of PHPUnit. Both testing frameworks are great. I use infection as mutation testing framework and I use the PHP code coverage extension on top of PHPSpec to have this code coverage. It's configured like this in the PHPSpec YAML file. Still quite small, but it's, you know, don't like this also infection. You configure your source directories? You can also exclude folders if you want during your, your tests. You can also have false positives. You can exclude them here as well. And I will now continue by my unit tests that I've prepared. The goal is that I will create a function that has an integer as an argument and it can it should not increment nor decrement, the value zero. So let's start with this one. I also have here just the class, this is the class I would like to write a unit test for. So this foo bar function, when it has the value zero, it should be zero. When we also implement this and we run our tests,

Yay. The first unit test is written, we still have two tests to do.

So, it's also should increment a positive number. So this foo bar of the value let's say five should be six. Now when we run our tests, this is incorrect obviously. So we change our implementation by checking if the number is zero, then we return zero, else we do number plus one. The second test did. Now I will also do this for the decrement function. Yes. So let's say a minus 10 should be minus 11 and then we have, if the number is smaller,

Zero return number minus one

We have successfully created a unit test with PHPSpec. On top of that, we use code coverage and we have a code coverage of 100% no bugs in here. So let's run our mutation testing framework. Now on top of it, we didn't achieve here. 100% well, this is an example where we can change our code since our tests are fine and this is a workaround. So we can either exclude this one or we can just change it

To this. I did a mistake. Number menus one. There we go. Yep. Like this.

So when we run our tests again, everything is still okay. We didn't make any major change, we switched those statements. But when we run our mutation framework on top of it, it's everything is good, well I forgot to mention something here. So let me go back to the initial setup. So sorry about that. Here we have the escaped mutant. Why? We can see it in our infection log file. And here we can see that's on line 15 of our foo bar class. It actually tried to change greater than zero to greater than or equals to zero. But since this is not a case in our code, it can never reach it. Since our first statement is already checking for equals to zero, we we can, you can change it upwards to make sure that everything is working correctly. And now you see that every mutant is killed. Now are these tests actually testing something, no they are not. Why? For this very basic example, there are some tests missing and this is what I would like to call the boundary or the limits. And the first positive number is one, and the first negative number is minus one. But what if we change our coat and let's say free,

These tests are still green and I've done a modification to the code. Obviously in this case this is this has no meaning, but it can happen that you have these huge functions with unit tests. There are actually not testing something. And another developer makes a change and thinks, Oh, the tests are still green, but actually it's not. So let me put this back to zero and add as well the first positive number, that should be two, as well as the first negative number should be minus two. I will now demo it again with the value of free. We will see that one of our tests failed. Now with infection. This is actually a mutator. I currently haven't configured it. That's why it's failing right now as well as the unit tests is failing so they can get correct again, that's about it for this brief demonstration. So, what did we actually learn today?

## What did we learn today?

This guy is Peterson Ted is really famous cook in Belgium and at the end of his shows he always asks the candidates a few questions about what did they learned? Well, what did I learn from this is always write unit tests. Writing unit tests is never a waste of time. Make sure that your whole team keeps them always up to date. Next is good coverage can give us a false positive feeling. But mutation testing gives us a slightly better quality indication, but it's not the Holy grail that will solve every application that contains no bugs anymore. So it's another metric that you can use that you can integrate in the CI environment. Still it takes a lot of time. So most developers would not like to run them every time in a git commit on their machine. So that's where I would like to place them. And that's the end of my quick talk. If there are questions, feel free to ask them. And thank you very much.

Hello? Hi, I'm is who feel extra tight costs of I will ask in English. Yeah. How many, how much extra time does it actually cost to run this mutation? That's a lot. A lot really. I, I haven't any metric included in this slide, but let's say that projects with these big unit tests that with code coverage take five minutes, it can go up to 20, 25 minutes. So it increased heavily really on time and that's why a referred to it to include it in a CI environment since we as a developer will not wait to get to it until it's finished.

Thank you.

## Questions

Hey, thanks for your talk. Thank you. Yeah, I had a quick question. So the configuration that you showed for the mutators it was for the whole project. Would you recommend that you would have specific mutator configurations per unit test or per unit test suite because obviously it has a exponential effect on the runtime or, or would you say that the whole project has just one big configuration for the entire mutators?

Yeah, that's a tough question. I would recommend to you is the complete list, but this takes so much time. Maybe you can be aware of these mutators that you will check them yourself. But I would recommend to use the whole list actually that you make sure that every tiny mutation is tested. Okay. Thanks.

Hey. so the way that I understood this is that every, a mutation is a shingle single change somewhere and then all the tests gets run. Yes. Is that necessarily so, because why? Why don't we try and apply a number of mutations and run the tests and that way try to improve the overall time that this takes because sure, it will not give you like the exact check to this one change led to this test failure. But if you get a list of like these 10 changes led to these five test failures in like a fifth of the time, then that may already be very helpful to you as well. That's true. That's true. But maybe, maybe you should ask this also to one of the maintainers of a infection, but how do I see it? Is that they want to do one modification and run the complete suite about over it to make sure that this particular mutation is seen by at least one test. I think that's the point of it, but honestly, I don't know. It's more in depth. I'm sorry. Okay. have a great day and enjoy the conference. Thank you.
