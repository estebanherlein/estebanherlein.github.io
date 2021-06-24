---
title: "CI/CD Teams"
categories:
  - Blog
tags:
  - Devops
  - AWS
---

AWS recommends organizing three developer teams for implementinga CI/CD environment:
<ul>
<li>application team</li>
<li>infrastructure team</li>
<li>tools team.</li>
</ul>

This organization represents a set of best practices that have been developed and applied infast-moving startups, large enterprise organizations, and in Amazon itself. The teams should be no larger than groups that two pizzas can feed, or about 10-12 people. This follows the communication rule that meaningful conversations hit limits as group sizes increase and lines of communication multiply

<h2>Application Team</h2>

The application team creates the application. Application developers own the backlog, stories, and unit tests,and they develop features based on a specified application target. This team’s organizational goal is to minimize the time these developers spend on non-core application tasks. In addition to having functional programming skills in the application language, the application team should have platform skills and an understanding of system configuration. This will enable them to focus solely on developing features and hardening the application. 

<h2>Infrastructure Team</h2>

The infrastructure team writes the code that both creates and configures the infrastructure needed to run the application. This team might use native AWS tools, such as AWS CloudFormation, or generic tools, such asChef, Puppet, or Ansible. The infrastructure team isresponsible for specifying what resources are needed,and it works closely with the application team. The infrastructure team might consist of only one or two people for a small application. The team should have skills in infrastructure provisioning methods, such as AWS CloudFormation or HashiCorp Terraform. The team should also develop configuration automation skills with tools suchas Chef, Ansible, Puppet,or Salt.

<h2>Tools Team</h2>

The tools team builds and manages the CI/CD pipeline. They are responsible for the infrastructure and tools that make up the pipeline. They are not part of the two-pizza team, however they create a tool that isused by the application and infrastructure teams in the organization. The organization needs to continuously mature its tools team,so that the tools team staysone step ahead of the maturing application and infrastructure teams. 

The tools team must be skilled in building and integrating all parts of the CI/CD pipeline. Thisincludesbuilding source control repositories, workflow engines, build environments, testing frameworks, and artifact repositories. This team may choose to implement software such as AWS CodeStar, AWS CodePipeline, AWS CodeCommit, AWS CodeDeploy, and AWS CodeBuild, along with Jenkins, GitHub, Artifactory, TeamCenter, and other similar tools. 