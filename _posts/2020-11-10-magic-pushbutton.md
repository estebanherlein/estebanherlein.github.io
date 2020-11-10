---
title: "Magic pushbutton"
categories:
  - Blog
tags:
  - Software design anti-pattern
  - Software design anti-pattern
---

A common anti-pattern in graphical user interfaces.

At its core, the anti-pattern consists of a system partitioned into two parts: user interface and business logic, that are coupled through a single point, clicking the "magic pushbutton" or submitting a form of data. 

As it is a single point interface, this interface becomes over-complicated to implement. The temporal coupling of these units is a major problem: every interaction in the user interface must happen before the pushbutton is pressed, business logic can only be applied after the button was pressed. 

Cohesion of each unit also tends to be poor: features are bundled together whether they warrant this or not, simply because there is no other structured place in which to put them. 


<h1>How to avoid the magic pushbutton</h1>

In a modern system, i.e. one where processing is cheap and competing interface standards are high, users should simply not be left to enter data for long periods without some automatic interaction to guide, validate, or to tailor the system according to the developing state of the data they've so far entered. 

Leaving them alone to "just get on with it", then validating everything at the end, means that the corrections needed will be detected further and further from when that data was entered. 

As an a priori principle, corrections needed should be highlighted as soon and as close to when they are either entered, or could first be identified.

In an event-driven interface, most events triggered by the "completion" of a field will present an opportunity to either validate that field, or to guide the choices for entering the next.

 They may even control which field the user is taken to next: sub-sections of a form are often made relevant or irrelevant by values entered early on, and users should not need to manually skip these, if it can be done for them.

In this scenario, the programmer draws the user interface first and then writes the business logic in the automatically created methods. 