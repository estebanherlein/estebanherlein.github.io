---
title: "Scaling test automation"
categories:
  - Blog
tags:
  - software testing
  - bug hunting
---


Writing automated tests that run perfectly against one environment it's  challenging in and of itself, but what  about when you're ready to scale your one suite of tests to run in multiple  environments, browsers and devices?

<h1> Considerations for scaling your test  automation projects</h1>

At some point in  your automation journey you may find the  need to run your automated scripts on  different environments. However you may  find that different environments have different information such as it's IP  address or URL, the login credentials, the  database information, etc.

For this reason , it's best to extract out these sort of  details from within your automation projects and make use of artifacts; they are like  properties files.

Even during your early phases of automating for a single environment, making these considerations early will prevent you from needing to  refactor later.

With the use of  properties files you can focus on the  content of the test.

In comparison to coding  multiple conditional paths, managing test  data in all other artifacts needed for test automation also becomes more  challenging when running across multiple  environments .

Fortunately solutions such as containerization help mitigate some of this burden. 

Even if executing on the same environment there may be a need to execute your UI tests across multiple  browsers, this is one of the benefits of  automating tests so that your testers do not have to repeat the same test over and over on various browsers and their versions. However, managing these browsers becomes a new task for your team.


Give  this serious consideration and determine if testing on a selectED set of browsers is sufficient, if the risk is too great  consider using cloud solutions that have an array of browsers of all different versions readily available to run against at any given time.


In today's  world, users tend to access application from all types of devices. This is another factor to consider when  developing your test.

Similar  considerations to the cross-browser testing needs to be made for cross-device testing:

<b> Will you create and maintain your own device form or is it more feasible to use a cloud-based service?</b>

For this  you'll also need to consider your test code as well so your UI level tests work when your application is in responsive  layout.

If some of the elements are replaced  with mobile friendly ones your test code should be able to handle this.

<b>For your native mobile applications, can your automation suite run for both iOS and Android? Do you need to write two different automation projects to support each of these?</b>

 This poses an interesting problem, there are libraries such as IBM that support writing an automated test once and having it run against different  mobile operating systems. However, if you  anticipate your developers helping with test automation: Which language should  this be written in?

 If you have two  unique native apps where your iOS  developers are writing in one language  and your Android developers are writing  in another language there is no common  denominator here. 

 If your native  mobile applications are distinctly  different meaning different features and  different navigational paths how will  you conquer this within your test code?

 These are critical decisions that need  to be made early on so that you don't go  down the path of automating for one of  these devices and then being unable to  later scale it to run against others  