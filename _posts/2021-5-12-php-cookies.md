---
title: "PHP and Cookies"
categories:
  - Blog
tags:
  - php
---

Web servers are typically stateless entities. That is to say they serve up web pages without regard to who requested the page and with no knowledge of whether that person has previously requested other pages. This makes it difficult for web based applications to track whether a visitor is new to the site or whether they have visited before and have already logged into a service. Cookies were developed to provide a mechanism to track state in the otherwise stateless world of the web.

Cookies essentially provide a mechanism to store small pieces of data on the computer systems of the visitors to your site. This enables you to maintain the state of a user's visit to your site so that you can track their movement through the site, or to store information such as their user name and address after they have entered it on one page so that they don't have to keep re-entering it on different pages.

Before going too far in implementing cookies on your web site it is important to keep in mind that users can disable cookie support in their browsers. You should, therefore, avoid making your site completely dependent on cookies. 

<h2>Difference Between Cookies and PHP Sessions</h2>

Both cookies and PHP sessions allow you to store data that is accessible across different pages of your web site, but there are differences between the two approaches.

Cookies are stored on the hard drive of the visitor to your site and are, therefore, visible to other domains you may host and run. They also have a long life and can be configured to persist long after the user has left your site. Cookies are limited in size and quantity (4kb each and a maximum of 20 cookies per domain).

PHP sessions, on the other hand, are stored on the web server. This means they are not visible to other web servers you may have hosting your domain. They are also not limited in size and can be used for storing secure data, since they are not transmitted to the client browser in the way that cookies are. 

<h2>The Structure of a Cookie</h2>

Cookies allow data to be stored in the form of a name/value pair. Both the name and the value are set at your discretion. For example you might want to write a cookie that stores the user name in the form username=JohnW. The cookie also contains additional information such as an expiration date and a domain.

The format of a cookie is as follows:

<pre><code>
name=value; expires=expirationDateGMT; path=URLpath; domain=siteDomain
</code></pre>

<h3>Cookie Name / Value Pair</h3>

The first section of the cookie defines the name of the cookie and the value assigned to the cookie. As previously mentioned, both the name and value settings can be anything you choose to use. For example, you might want save a user's currency preference - currency=USDollars. 

This is the only section of the cookie that is mandatory, the rest are entirely optional. Whether or not you use these optional settings depends on your specific requirements. The following settings, therefore, can be omitted from the cookies if they are not required.

<h3>Cookie Expiration Setting</h3>

The optional expires= section specifies the date on which the associated cookie should expire. The PHP time() function can be used to obtain and manipulate dates for this purpose as we will examine later in this chapter.
Cookie path Setting

The path= setting allows a URL to be stored in the cookie. By default, cookies are accessible only to web pages in the same directory as the web page which originally created the cookie. 

For example, if the cookie was created when the user loaded http://www.example.com/intro/index.html that cookie will be accessible to any other pages in the /intro directory, but not to pages in /navigation. By specifying path=/navigation this limitation is removed.

<h3>Cookie domain Setting</h3>

Similar to the path setting, cookies are only accessible to web pages residing on the server domain from which the cookie was originally created. For example, a cookie created by a web page residing on www.example.com is not, by default, accessible to a web page hosted on www.example.org. Access to the cookie from web pages on example.org can be enabled with a domain=example.org setting.
Cookie Security Setting

This setting controls whether the cookie is transmitted using insecure HTTP or secure HTTPS. 

<h2>Creating a Cookie in PHP</h2>

Cookies are created in PHP using the setcookie() function. setcookie() takes a number of arguments. 

The first argument is the name of the cookie (the name part of the name/value pair described earlier). The second is the value part of the name/value pair. The third argument is the optional expiration date of the cookie. The fourth argument specifies the active path for the cookie. The fifth argument is the domain setting and the sixth is the security setting (0 specifies HTTP and HTTPS and 1 specifies HTTPS only). 

<h2>Reading a Cookie in PHP</h2>

Given that you've gone to the trouble of writing a cookie it stands to reason you'll probably want to read it back at some point. This is achieved by accessing the $_COOKIE array. The $_COOKIE array is an associative array whereby the name of the cookie provides the index into the array to extract the corresponding value of the name/value pair (for details of PHP arrays read the PHP Arrays chapter of this book. 