---
title: "Intro to docker"
categories:
  - Blog
tags:
  - Linux
  - Docker
---

Let's talk about docker and the buzzword containers.

<h1>What is docker</h1>

Docker is designed to build, ship and run business critical applications in production at scale.

You can build and share containers and automate the development pipeline from a single environment. Each of these containers represents a piece of the app or system.

Let's talk about how docker makes all of this work at a higher level.

Containers are the building blocks of the containerization world and allow you to package only the things you need for your application or service without creating whole operating systems like virtual machines.

This means they are faster and more lightweight. Containers also give you control over your environments because you can specify exactly what you want each container to look like by using blueprints called images.

Images are the specs or details used to create containers just like how images for VMs lets you spin up a windows instance of Vista or XP or Linux images lets you pick between ubuntu debian or other versions images for docker, lets you specify which services libraries or dependencies you need for a container.

To make this even easier to understand, you can think of images as a very detailed shopping list. 

If our app was a peanut butter and jelly sandwich we would have three main ingredients: peanut butter, jelly and bread. 

If we had to make this sandwich manually it would be up to the author of this poetic beautiful sandwich to decide where they get these ingredients and the brands and types they want. Because of this it would be very easy for two authors to have drastically different sandwiches. 

Images would solve this by having a very detailed specification for each of these ingredients, there would be no way for me to get the wrong and or flavor if I knew exactly what to get.

If we look at the structure of a very simple web application, there are four pieces that make up the entire app:

<ul>
<li>the database, that stores our information.</li>
<li>the API layer, to communicate between the UI and the database.</li>
<li>the front-end code, that is the UI</li>
<li>the web server, to host the UI and application</li>
</ul>

Without containers organizations would have to manage each one of these manually.

This is a super simple example for just one environment, but we already have to track things like which environments of the front-end code are we running on, which dependencies are required and what are their versions. Networking the services so they are connected correctly , managing services as each one changes and the list goes on.

This is why companies struggle when trying to implement their own CI/CD. 

