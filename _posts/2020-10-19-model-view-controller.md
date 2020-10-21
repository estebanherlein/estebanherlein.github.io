---
title: "Model - view - controller"
categories:
  - Blog
tags:
  - software design patterns
---

Model-view-controller , also known as MVC, is a software design pattern that separates the business logic from the user interface and the code that manages interactions between them.

MVC divides the app into three different components:

<ul>
<li>
Model: Representation of the information with which the system operates, manages access to said information, both queries and updates. It sends to the 'view' the information that is requested to be displayed. Requests come to the 'model' through the 'controller'.
</li>
<li>
Controller: Reacts to events and invokes requests to the 'model'. You can also send commands to its associated 'view' if a change is requested in the way the 'model' is presented (for example, scroll through a document), therefore It could be said that the 'controller' acts as an intermediary between the 'view' and the 'model' .
</li>
<li>
View: It presents the 'model' (information and business logic) in a suitable format to interact (usually the user interface).
</li>
</ul>

<h2>Control Flow</h2>

<ol>
<li>The user interacts with the interface in some way (for example, the user clicks a button, link, etc.)</li>

<li>The controller receives the notification of the action requested by the user. The controller handles the arriving event, often through an event handler or callback.</li>

<li>The controller accesses the model, updating it, possibly modifying it appropriately to the action requested by the user (for example, the controller updates the user's shopping cart). Complex controllers are often structured using a command pattern that encapsulates the actions and simplifies their extension.</li>

<li>The controller delegates to the objects in the view the task of displaying the user interface. The view gets its data from the model to generate the appropriate user interface where changes to the model are reflected (for example, it produces a list of the contents of the shopping cart). </li>

<li>The UI expects new interactions from the user, starting the cycle all over again</li>

</ol>
