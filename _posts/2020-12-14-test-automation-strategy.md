---
title: "Designing a test automation strategy "
categories:
  - Blog
tags:
  - software testing
  - bug hunting
---

Let's take a moment to consider what is your goal for starting a test automation initiative and what is it that you want to accomplish, who do you envision participating in your test automation initiative and in what capacity and how do you plan for the execution of this strategy 

<h1>What is your goal</h1>

Is it to reduce the time that it takes to execute regression testing?

Perhaps your team needs to release features faster so you want to reduce the manual effort it takes to run the regression test and allow your testers to focus on testing the new features, or perhaps your goal is to reduce technical debt by closing your Sprint's with test automation in place for the new features
 
As your developers are creating new features and your testers are verifying them there's not much time for full-on manual regression testing and closing the sprint without automating the newly identified test only adds to that problem so maybe you want to take care of this early on or perhaps your goal is to enable continuous testing as part of your build process after checking in new features.

Your developers may want the confidence that what they've added isn't compromising the overall quality of the application. 

Adding automated tests to your continuous integration pipeline cancertainly help with this the key here is to understand what it is you're trying to accomplish.

Before you begin any planning take a moment to decide why it is that you need test automation, make sure this goal is at the forefront of all of your decisions because your subsequent actions in regards to test automation should be aimed toward this goal.

Who gets involved, the tools you use, which tests you automate, the execution strategy; all of this should be aligned with your goal.

Communicate the goal to the entire team make sure everyone is aware of why the team is doing test automation and what it is you all wish to accomplish by it.

I stress this because many teams jump into the implementation of test automation without taking a moment to consider why they are doing it.

This leads to failed automation projects where teams are unprepared for the issues that present themselves and are unsatisfied with the return on their investment.

<h1>What to consider? </h1>

Let's have a look at considerations that should be made when defining your strategy.

<h2>Who do you envision participating in your test automation initiative and in what capacity</h2>

Before answering this let'stalk about the implications of automating your regression test.

You need someone to write the test automation scripts, you need someone to monitor the results every time the tests are run, you need someone to update the test when the behavior of the application changes.

These tasks can all be done by the same person or shared amongst the team but let's explore this a bit.

Who's going to write your tests; let's say you choose the developers because hey they already know how to code.

Well your developers are working on new features, will they realistically have the time to work on scripting regression tests?

Let's say you choose the manual testers as the ones to write the test scripts because hey they're better at testing anyway. Let's remember the problem we're solving you're investing in test automation as a way to reduce the time and effort required for regression testing; can you now spare the testers to not only test new features but also to spend time automating old tests?

Here's the hard truth unless you're able to pull your developers or testers off of their current task of working on new features or you're able to provide them with the time and resources needed to do these tasks these may not be your best options make no mistake test automation is a software development project in and of it self, it takes a considerable amount of time and skill to do it if you treat it as a sidetask that people only contribute to whenever they have time it will fail even if you're able to find the time to allow your developer or tester to write the automated scripts there's still the task of monitoring them and updating them as needed.

<h2>Who should work on test automation?</h2>

You have a couple of options here some companies assign someone to temporarily work on automating their regression backlog, however this only works if you have another plan and strategy for future tests otherwise the regression backlog will continuously grow as new features are developed and you'll find yourself back at square one.

Another option is to assign someone to permanently work on your test automation, this becomes their full-time job and yes in most cases it is indeed a full-time job. You can assign a developeror a tester to this role or have them work together as a pair but be sure to account for the fact that either these would have to invest in learning test automation.

Yes, your developer knows how to code but how familiar is him with testing and test automation.

Your tester understands testing but how familiar is he with development and test automation.

Don't get me wrong this strategy can certainly work but you must be realistic about the learning curve in time investment and it also really helps if the person actually wants to do this work.


Another great alternative is to employ a test automation engineer, this person is ideally skilled in testing as well as automation development. They can lead your test automation efforts and include the developers in the test in  a more reasonable capacity.

If you take this route is critical that you make this person a standard part of your team, having them interact and collaborate with the rest of the team members will strengthen your test automation initiative.


Now if none of these options seem possible ask yourself: if you'reviewing this as a side project are you willing and capable of investing what is required for this to succeed.

Let's say you define your strategy and you have an idea of who will lead the effort as well as how others will contribute the final thing .

<h2>Planning the Execution</h2>

Let me offer a question to ponder, when your team was executing these regression tests manually, did they run all of them everytime or did they make a strategic decision based on other factors such as risk and value. You may think that since you're automating these tests you might as well automate all of them but there is a cost that comes with automation: the time and the maintenance required is not something to be taken lightly.

Automated tests need a clear understanding of the scenarios, the actions and clearly defined expected results.

This may be covered by acceptance tests or test cases and while verbal communication is wonderful a written summary of expectations, even if light, is extremely helpful when writing test automation.

The test script authors  swap from creation mode to verification mode as they're writing the test code, so having a guide to consult with to ensure nothing is missed is key.


You need to choose tools for your automation project such as a programming language just as with your development projects you'll also want to develop standards and conventions especially if you envision multiple people contributing to the automation project.

<h2>How will the tests be executed</h2>

Is it okay to have someone kick them off when needed and report back with the results or do you want them executed multiple times a day within their own CI job, where everyone has visibility into the results, or do you want them integrated into your development CI job where they're executed anytime someone checks in new code.

Each one of these requires a certain level of trust and focused attention.

Let's look at each one

Running the automated tests locally and reporting the results to the team requires manual intervention and therefore will indeed be slower but the result reported to the team have already been triaged and can be trusted to be accurate.


Running the test multiple times a day in a CI job separate from development gives faster feedback but the reported results have not yet been triaged so the tests themselves have to be written with a greater level of proficiency and care to ensure that they're not flaky and that they can be trusted.

Running the tests as part of development CI process requires fast and reliable tests that only fail when the application under test has provoked it to.

I recommend gradually moving to these phases starting out with running locally or as part of a private CI job that is not exposed to others this will allow you to learn more about what causes your test to be flaky including quirks about your application. 

Once you find that you can trust your tests yourself move to a separate CI job that is visible to everyone.

Once you are very confident in your test only then should you get them added to the development CI process it's best to realize early on that your test failures will need to be triaged and maintainedand plan for this 

<h1>A test automation project is a development project</h1>

Remember your strategy on an automation project is a software development project and as the development of your product changes, so does your automation code.

I cannot stress this enough it's not an optional task, your automated tests will need to be triaged and maintained so plan accordingly.

The good news is that this is a great opportunity for others on the team to assist as your developers run tests to verify that their new features didn't break any of the existing ones. They can be responsible for triage and any failures, ideally any tests that fail will be due to their changes and therefore they can fix their code or update the test to reflect the new expectations of the application.

However, you need to also be prepared for unrelated tests to fail as well, this will give developers insights into things that cause flaky tests and ways that they can improve the tests automate-ability of the application.

Manual testers are also a valuable option for triage and automation failures especially ones who have an interest in contributing to the automation code base, reviewing test failures, debugging the automation code and updating the code when needed are great introductory opportunities into test automation.

While all developers and testers can certainly assist in the triage and updating of test automation scripts, because it is not their primary responsibility, there's still a need for someone to monitor this consistently. 

Unmonitored tests are untrustworthy tests.

As your team continues to lose trust in the automated test they tend to rely less on them and the automation project eventually dies