---
title: "How does php work?"
categories:
  - Blog
tags:
  - php
---

PHP is an intuitive, server side scripting language. 
Like any other scripting language it allows developers to build logic into the creation of web page content and handle data returned from a web browser. 

PHP also contains a number of extensions that make it easy to interact with databases, extracting data to be displayed on a web page and storing information entered by a web site visitor back into thedatabase. 

PHP consists of a scripting language and an interpreter. 

Like other scripting languages, PHP enables web developers to define the behavior and logic they need in a web page. These scripts are embedded into the HTML documents that are served by the web server. 

The interpreter takes the form of a module that integrates into the web server, converting the scripts into commands the computer then executes to achieve the results defined in the script by the web developer

<h2> How does it work?</h2>

To develop an understanding of how PHP works it is helpful to first explore what happens when a web page is served to a user's browser.

When a user visits a web site or clicks on a link on a page the browser sends a request to the web server hosting the site asking for a copy of the web page. The web server receives the request, finds the corresponding web page file on the file system and sends it back, over the internet, to the user's browser. 

Typically the web server doesn't pay any attention to the content of the file it has just transmitted to the web browser. As far as the web server is concerned the web browser understands the content of the web page file and knows how to interpret and render it so that it appears as the web designer intended. 

Now let's consider what kind of web page content a web browser understands. 

These days a web page is likely to consist of HTML, XHTML and JavaScript. The web browser contains code that tells it what to do with these types of content. 

For example, it understands the structure HTML in terms of rendering the page and it has a JavaScript interpreter built in that knows how to execute the instructions in a JavaScript script. 

<b>A web browser, however, knows absolutely nothing about any PHP script that may be embedded inan HTML document.</b> 

If a browser was served a web page containing PHP it would not know how to interpret that code. Given that a web browser knows nothing about PHP in a web page, then clearly something has to be done with any PHP script in the page beforeit reaches the browser. 

This is where the PHP pre-processing module comes in. The PHP module is, as mentioned previously, integrated into the web server. The module tells the web server that when a page is to be served which contains PHP script (identified by special markers) that it is to pass that script to the PHP pre-processing module and wait for the PHP module to send it some content to replace that script fragment. 

The PHP processing module understands PHP, executes the PHP script written by the webdeveloper and, based on the script instructions, creates output that the browser will understand. The web server substitutes the content provided by the PHP pre-processor module in place of the PHP script in the web page and sends it to the browser where it is rendered for the user to view.