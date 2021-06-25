---
title: "Deployment Methods"
categories:
  - Blog
tags:
  - Devops
  - AWS
---

You can consider multiple deployment strategies and variations for rolling out new versions of software in a Continuous Delivery process. The most common deployment methods are: 
<ul>
<li>All at once(deploy in place)</li>
<li>Rolling</li>
<li>Immutable</li>
<li>Blue/Green.</li> 
</ul>

<h3>All at Once (In-PlaceDeployment)</h3>
All at once or in-place deployment is a method you can use to roll out new application code to an existing fleet of servers.

This method replaces all the code in one deployment action. It requires downtime because all servers in the fleet are updated at once. There is no need to update existing DNS records. In case of a failed deployment, the only way to restore operations is to redeploy the code on all servers again. 

<h3>Rolling Deployment</h3>

With rolling deployment, the fleet is divided into portions so that all of the fleet isn’t upgraded at once. During the deployment process two software versions, new and old, are running on the same fleet. This method allows a zero-downtime update. If the deployment fails, only the updated portion of the fleet will be affected. 

A variation of the rolling deployment method, called canary release,involves deployment of the new software version on a very small percentage of servers at first. This way, you can observe how the software behaves in production on a few servers, while minimizing the impact of breaking changes.

If there is an elevated rate of errors from a canary deployment, the software is rolled back. Otherwise, the percentage of servers with the new version is gradually increased.

<h3>Immutableand Blue/Green Deployment</h3>

The immutable pattern specifies a deployment of application code by starting an entirely new set of servers with a new configuration or version of application code. This pattern leverages the cloud capability that new server resources are created with simple API calls.The blue/green deployment strategy is a type of immutable deployment which also requires creation of another environment. Once the new environment is up and passed all tests, traffic is shifted to this new deployment. Crucially the old environment, that is,the “blue” environment, is kept idle in case a rollback is needed.