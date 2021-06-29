---
title: "CI/CD Best Practices"
categories:
  - Blog
tags:
  - Devops
  - AWS
---
<h2>Do</h2>
<ul>
<li>Treat your infrastructure as code
<ul>
<li>Use version control for your infrastructure code.</li>
<li>Make use of bug tracking/ticketing systems.</li>
<li>Have peers review changes before applying them.</li>
<li>Establish infrastructure code patterns/designs.</li>
<li>Test infrastructure changes like code changes.</li>
</ul></li>
<li>Put developers into integrated teams of no more than 12 self-sustaining members.</li>
<li>Have all developers commit code to the main trunk frequently, with no long-running feature branches.</li>
<li>Consistently adopt a build system such as Maven or Gradle across your organization and standardize builds.</li>
<li>Have developers build unit tests toward 100% coverage of the codebase</li>
<li>Ensure that unit tests are 70% of the overall testing in duration, number,and scope.</li>
<li>Ensure that unit tests are up-to-date and not neglected. Unit test failures should be fixed, not bypassed.</li>
<li>Treat your continuous delivery configuration as code.</li>
<li>Establish role-based security controls(that is,who can do what and when).
<ul>
<li>Monitor/track every resource possible.</li>
<li>Alert on services, availability, and response times.</li>
<li>Capture, learn, and improve.</li>
<li>Share access with everyone on the team.</li>
<li>Plan metrics and monitoring into the lifecycle.</li>
</ul></li>
<li>Keep and track standard metrics.
<ul>
<li>Number of builds.</li>
<li>Number of deployments.</li>
<li>Average time for changes to reach production.</li>
<li>Average time from first pipeline stage to each stage.</li>
<li>Number of changes reaching production.</li>
<li>Average build time.</li>
</ul></li>
<li>Use multiple distinct pipelines for each branch and team.</li>
</ul>

<h2>Don’t:</h2>
<ul>
<li>Have long-running branches with large complicated merges.</li>
<li>Have manual tests.</li>
<li>Have manual approval processes, gates, code reviews, and security reviews.</li>
</ul>
