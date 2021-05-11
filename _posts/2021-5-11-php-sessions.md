---
title: "PHP Sessions"
categories:
  - Blog
tags:
  - php
---

PHP Sessions allow web pages to be treated as a group, allowing variables to be shared between different pages. 

One of the weaknesses of cookies is that the cookie is stored on the user's computer (and by user we mean the person with the browser visiting your web site). This provides the user the ability to access, view and modify that cookie for potentially nefarious purposes. 

PHP sessions, on the other hand, store only an ID cookie on the user's system which is used to reference the session file on the server. As such, the user has no access to the content of the session file, thereby providing a secure alternative to cookies. 

PHP sessions also work when the user has disabled the browser's cookie support. In this situation it includes the session ID information in the web page URLs. 

<h2>Creating a PHP Session</h2>

PHP sessions are created using the session_start() function which should the first function call of the PHP script on your web page (i.e. before any output is written to the output stream). 

<h3>Creating and Reading PHP Session Variables</h3>

Variables can be assigned to a session using the $_SESSION array. This is a global array that is accessible to all the pages on your web site. This is also an associative array (see PHP Arrays for details of using arrays in PHP) and as such it is possible to access array elements using the variable name as an index.

Session variables can be any type of data such as strings, numbers, arrays and objects. 

Another option is to use the PHP session_register() function. session_register() takes two arguments, the string representing the variable name, and the value to be assigned to the variable. 

<h3>Writing PHP Session Data to a File</h3>

Session data only stays active on the web server until it expires or the session is deleted. Once deleted, all the data associated with the session is lost. A snapshot of the session data can, however, be taken at any time and written out to a file. Once saved, it can be reloaded when required.

To save a session state the session_encode() function is used combined the PHP file I/O functions. The session_encode() function returns an encoded string containing the session data. 

Once this string has been obtained it can be written to a file

<h3>Reading a Saved PHP Session</h3>

Once session data has been written to a file it can be read back in, decoded and applied to the current session. This is achieved using the session_decode() function: 