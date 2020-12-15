---
title: "Test automation culture"
categories:
  - Blog
tags:
  - software testing
  - bug hunting
---

Test automation is most successful when there is collaboration amongst different team members: the product owners, business analysts,  developers, testers and of course automation engineers.

<h1>Define a strategy</h1>

Defining the strategy is an essential first step to a successful test automation initiative, but all of your hard work can still come unraveled if your organization does not possess a culture that supports your goals. 


Let's discuss how to get people on board, how to help them understand their place in the automation strategy and how to enable them to do what's needed.

It's very important to communicate the goal of your test automation endeavour and make sure everyone understands what's needed to accomplish that goal; and more importantly the role that they play in realizing the success of it.

If the goal is to receive fast and pertinent feedback then automation in every test is not in line with this goal.

<h1>Product owners</h1>

Your business analysts and product owners can assist here they help provide the business context to the features that are developed and can also do the same for related tests, they can provide their insight on which tests provide the most value and therefore should be automated and run at every check-in.

Make sure to help them understand this role that they can play in making test automation more efficient and enabling the entire team to move faster.

When the product owner understands the goal and purpose of test automation they will also be a key advocate in pushing for the health of the automated tests, if there are tests that are failing and your team finds it self in a position where no one has the time to update the test your product owner should realize that without this safety blanket the developers are not able to move as fast as they could if the automated tests were trustworthy.

I've seen product owners who are so invested that they included these test automation/maintenance tasks in the product backlog and prioritize them with feature work. This is the level of involvement that keeps automation goals and impact at the front of everyone's minds.

<h1>Developers</h1>

Developers are able to move faster with their future development, this is because they don't need to be as fearful about the impact that their coed may cause to the existing code-base because they can quickly run the automated tests against their new changes and fix anything that may have broken before actually integrating the code.

But it's important to help your developers understand that in order to reach this point they have to contribute to the initiative.

Devs should contribute with unit tests to the overall test automation project, these are small tests that verify the logic of individual functions without the need for integration of other functionality, databases or user interfaces.

Another critical area of focus for developers is to ensure that the areas that they are delivering can be easily automated against.

Developers can also assist in updating tests that fail due to new changes that they have made, this is an activity best done by them because it forces them to answer the question of:

>"is the change in expected behavior valid ?"

If the answer is no they can adjust their code before any damage is done. This fast feedback is extremely valuable so even without leading the test automation project developers can contribute a lot to its success.

However, these opportunities for collaboration are not always apparent to them be sure to spell it out and educate them on how their efforts help the overall goal. 


<h1>Don't forget about manual testing</h1>

Even with a successful test automation project you will still need your manual testers.

Many have made the mistake of believing that test automation is a replacement for testing. 

Testers are still needed to explore and thoroughly interrogate your applications they will be the ones who discover your most costly bugs. 

In addition to their testing they can also be a great help to the test automation initiative by providing insights on the tests that are best to automate in areas of the application that may need the most coverage by test automation.

For those interested in test automation they can also contribute to the triaging and maintenance of test scripts.

It's really important that your organization understands that test automation does not replace testing nor should it be treated as more valuable.

Truly believe in this and making sure your testers also understand it. This will foster a culture where testers embrace test automation and view it as an assistant to them versus a potential threat to their jobs