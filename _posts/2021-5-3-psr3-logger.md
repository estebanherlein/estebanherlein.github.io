---
title: "PSR-3 Logger Interface "
categories:
  - Blog
tags:
  - php
---

It describes a common interface for logging libraries.

The main goal is to allow libraries to receive a Psr\Log\LoggerInterface object and write logs to it in a simple and universal way. 

Frameworks and CMSs that have custom needs MAY extend the interface for their own purpose, but SHOULD remain compatible with PSR3. This ensures that the third-party libraries an application uses can write to the centralized application logs.

<h2>Why Use PSR-3?</h2>

The use of PSR-3 ensures the highest possible independence of the actual source code from the logging library ultimately used, since the interface is clearly defined. 

One advantage is that you can use a different library at any time without having to make any changes in your own source code. Just as important is the possibility that any external modules or components that implement PSR-3-compliant logging can be easily integrated into your own project and their logging is thus automatically integrated into the system's own logging.

Conversely, a self-created component based on PSR-3 logging can be integrated into third-party projects much faster.
 
<h2>The PSR-3 LoggerInterface</h2>

In order to log PSR3 compatible, it is necessary to examine the structure and methods of the logger interface more closely.

The interface provides 8 methods for creating log entries with the appropriate weighting. In addition, a general method is defined that receives the weighting of the entry to be created as the first parameter.

PSR3 defines the following levels based on RFC 5424 (defined in class LogLevel):

<ul>
<li>Emergency – the system is unusable</li>
<li>Alert – immediate action is required</li>
<li>Critical – critical conditions</li>
<li>Error – errors that do not require immediate attention but should be monitored</li>
<li>Warning – unusual or undesirable occurrences that are not errors</li>
<li>Notice – normal but significant events</li>
<li>Info – interesting events</li>
<li>Debug – detailed information for debugging purposes</li>
</ul>

All methods expect the message to be logged as the first argument. This must either be a string or an object that implements the __toString() method. In addition to plain text, the message can also contain placeholders in curly braces ({key}), which are replaced by the corresponding values from the context data, which can be passed as a second argument.

The context data in the second (optional) argument are passed as an associative array. Any additional information that is not necessarily available as a string can be transferred via this array. The presentation of this context data is in the responsibility of the implementation of the logger, whereby the context data should be treated by the logger as tolerantly as possible. The content of the context data will under no circumstances lead to any exception, error or warning.

Exceptions are a special case when transferring the context data. An exception can also be passed directly in the message argument (this is permitted since all exceptions implement the __toString() method), but it is better to provide this in the context array in the key 'exception'. The implementation of the logger have thus the option to include additional, more extensive information (such as the stack trace) in 