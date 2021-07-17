---
title: "Queue data structure"
categories:
  - Blog
tags:
  - Data Structures
---
We can define the queue data structure as a restrictive linear FIFO (first in firstout) type structure, this indicates that the first element that entered the queue must be the first to exit.

We can visualize a queue if we think, for example, of a queue in a supermarket. 

Let us suppose that we have a supermarket that has only one customer service checkout, in which, as customers who have already made their purchase arrive, they form a line to be able to pay for it. 

If customer A is the first to arrive, he will be in line first; then another client will arrive, B, which will be formed behind A, and finally, client C will arrive and will form behind B. This process is called the process of inserting into a queue.

Continuing with the example, when the checkout begins to serve customers, it will be served in the order of arrival, that is, in the order in which the customers are in the queue. In this sense, the first customer to be served will be A, the next customer will be B, and lastly, customer C will be served. 

<h2> Main characteristics of the queue data structure</h2> 

<ul>

<li>Elements can always be inserted last (behind the rest of the elements), leaving the element at the bottom of the queue</li>

<li>Element extractions can always be performed from the first place</li>

<li>To access the other data, necessarily, the rest of the elements must be extracted</li>

</ul>

<h2>Queue implementation example</h2> 

One of the cases of a queue type structure is the document printing processes. 

When we have a printer connected to a computer, the printer driver has to handle the printing of multiple documents, since a user can send different documents to print or different printing processes for the same document, for example, page range printing. 

To solve this problem, a queue type structure is used, commonly called a "print queue."

Each time the user submits to print a print "run" is created and inserted into the print queue.

As soon as the printer connects and is ready to start printing, what it does is read the information from the first process in the queue, make the print and, when it finishes with said process, it continues with the next one, for which it must "unglue" the element already processed. 

In this way, as printing processes are sent, they will be "glued" in the print queue and, as the prints are made, they will be "unglued" from the print queue.