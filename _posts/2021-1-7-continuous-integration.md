---
title: "Continuous Integration"
categories:
  - Blog
tags:
  - software testing
  - Dev-ops
---

Continuous Integration (CI) is a development practice that requires developers to integrate code into a shared repository several times a day. Each check-in is then verified by an automated build, allowing teams to detect problems early.

By integrating regularly, you can detect errors quickly, and locate them more easily.

<h1>Solve problems quickly</h1>

Because you’re integrating so frequently, there is significantly less back-tracking to discover where things went wrong, so you can spend more time building features.

Continuous Integration is cheap. Not integrating continuously is expensive.

If you don’t follow a continuous approach, you’ll have longer periods between integrations. This makes it exponentially more difficult to find and fix problems. Such integration problems can easily knock a project off-schedule, or cause it to fail altogether.

Continuous Integration brings multiple benefits to your organization:
<ul>
<li>Say goodbye to long and tense integrations</li>
<li>Increase visibility enabling greater communication</li>
<li>Catch issues early and nip them in the bud</li>
<li>Spend less time debugging and more time adding features</li>
<li>Build a solid foundation</li>
<li>Stop waiting to find out if your code’s going to work</li>
<li>Reduce integration problems allowing you to deliver software more rapidly</li>
</ul>

<h1>More than a process</h1>

Continuous Integration is backed by several important principles and practices.

<h2>The practices </h2>
<ul>
<li>Maintain a single source repository</li>
<li>Automate the build</li>
<li>Make your build self-testing</li>
<li>Every commit should build on an integration machine</li>
<li>Keep the build fast</li>
<li>Test in a clone of the production environment</li>
<li>Make it easy for anyone to get the latest executable version</li>
<li>Everyone can see what’s happening</li>
<li>Automate deployment</li>
</ul>
<h2>How to do it </h2>
<ol>
<li>Developers check out code into their private workspaces</li>
<li>When done, commit the changes to the repository</li>
<li>The CI server monitors the repository and checks out changes when they occur</li>
<li>The CI server builds the system and runs unit and integration tests</li>
<li>The CI server releases deployable artefacts for testing</li>
<li>The CI server assigns a build label to the version of the code it just built</li>
<li>The CI server informs the team of the successful build</li>
<li>If the build or tests fail, the CI server alerts the team</li>
<li>The team fixes the issue at the earliest opportunity</li>
<li>Continue to continually integrate and test throughout the project</li>
</ol>

<h2>Team responsibilities</h2>
<ul>
<li>Check in frequently</li>
<li>Don’t check in broken code</li>
<li>Don’t check in untested code</li>
<li>Don’t check in when the build is broken</li>
<li>Don’t go home after checking in until the system builds</li>
</ul>

Many teams develop rituals around these policies, meaning the teams effectively manage themselves, removing the need to enforce policies from on high.

By adopting both Continuous Integration and Continuous Deployment, you not only reduce risks and catch bugs quickly, but also move rapidly to working software.

With low-risk releases, you can quickly adapt to business requirements and user needs. This allows for greater collaboration between ops and delivery, fueling real change in your organization, and turning your release process into a business advantage.