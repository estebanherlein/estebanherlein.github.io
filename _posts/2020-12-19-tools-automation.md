---
title: "Test automation tools"
categories:
  - Blog
tags:
  - software testing
  - bug hunting
---

You have already defined your strategy for test  automation, you've put practices in place to build a culture that supports your  strategy.

You've reviewed key concepts on  building reliable tests as well as  making sure your application can be automated against.

Now is the time to  consider the tools for your test  automation project.

<h1>Choose the right tools for your initiative.</h1>

Before choosing your tools it's important to consider who will be using them. If you don't have  programmers who will actively contribute  to the test automation then building your own test automation framework may not be a valuable option.

Remember test  automation is software development, if  your idea is that you'll have your testers learn how to code and then create this brand-new software development project please realize that this takes quite a bit of investment in education for them.

Your organization should provide a massive amount of support for this, if that seems unrealistic there are tools on the market which allow your testers to record their scenarios and then execute them as part of regression testing.

While programming knowledge is not required note that you'll still need to plan for triaging and maintenance.

If you'll have your developers or your automation engineers do the automating then a coded solution is by far a better option.

It allows for  more control and flexibility, the bare  minimum you need for your test  automation project is an interaction  tool and a validation tool.

<h2>Interaction tools</h2>

Remember we  have three levels:

<h3>Unit tests</h3>


Unit tests and service tests that call production functions should be written in the same programming language and reside in the same project as the production code. Execution is simply the call to these functions. For other tests you have more options.

<h3>Service tests </h3>

Service level tests that call into api's  will need to be able to execute the HTTP calls and read through the responses so you'll want to look for a programming language that makes this easy or libraries that take care of the boilerplate work for you.

<h3>UI tests</h3>
For you UI you'll need a navigation library  which provides the ability to interact  with HTML elements of your application. Using a tool that supports  the programming language that your application is written in is a reasonable idea. However you should also  consider how easy it is to hire for that programming language , in case you want to expand and hire more additional automation engineers ,and also consider  how widely supported that programming  language is by test automation tools.

It's really beneficial to use tools that have an abundance of support and educational resources so if your team is  using an obscure programming language for its product development which has limited support and resources this might not be the best choice for your  automation project.

Another factor to  consider is the browsers and devices you need to run your test automation against  and ensure that the tools you choose are  supported for these options.

<h2>Validation tools</h2>

Let's move on to what is needed beyond interaction tools. You also need to include validation libraries, these are tools which will allow you to turn your code into a test which can pass or fail.

There are various options of these  validation libraries for the array of things that you need to verify, including  functional, visual, accessibility, security and so on. 

<h1>Conclusion</h1>

This is the bare minimum that you'll need for your automation project:
<ul>
<li>A way to execute the test </li>
<li>A way to  verify them</li>
</ul>

However you can certainly make your project more sophisticated by adding a reporting library, which shows screenshots and possibly even video of  test failures or the integration  gherkin scenario files if your team is already practicing behavior driven development and if your ultimate goal is to run the test as part of CI you'll want to choose tools that allow for this  integration.  