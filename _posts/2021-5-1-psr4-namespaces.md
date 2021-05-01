---
title: "PSR-4 and namespaces "
categories:
  - Blog
tags:
  - php
---
PSR-4 is a specification for auto-loading of classes from the file path. It describes where the files to be autoloaded are located. 

PSR-4 makes use of namespaces to distinguish one class from another, this is very helpful when we use third-party libraries because in many cases there will be classes with the same name as ours and they could be overwritten or use one that we do not want.

PSR-4 was created by the PHP interoperability group, they have worked on the creation of development specifications for this language so that we standardize different processes, such as in this case how to name the classes of our project and make use of them .

Using PSR-4 specifications is not mandatory and its use can be complete or partial, although it is recommended not to omit it because Composer allows you to load classes automatically.

<h2>What is an autoloader?</h2>

They appeared since the PHP5 version and allow us to find classes for PHP when we call the new () or class_exists () functions. This way we don't have to keep using require () or include ().

PSR-4 allows us to define namespaces according to the path of the class files, that is, if we have a "Pdf" class in the Clases / Templates / directory, that will be its namespace. We can do a simile with the import of java.

The Classes / Templates namespace would be as follows: Clases \ Templates \ Pdf.php

<h2>What is classmap?</h2>

It is an autoloader that allows us to register our classes to be able to occupy them without the need for a namespace, the disadvantage with respect to PSR-4 is the collision of classes with the same name, the main advantage is the speed of class autoloading. 

Another drawback of using classmap is that we must constantly execute the "composer dump-autoload" command for each new class in the directory that we indicate or have registered in the "composer.json" file.

<h2>Specifications</h2>

<h3>The term "class" refers to classes, interfaces, traits, and other similar structures.</h3>
<h3>A fully qualified class name has the following form:</h3>

<pre><code>
\< NamespaceName >(\< SubNamespaceNames >)*\< ClassName >
</code></pre>
<ul><li>The fully qualified class name MUST have a top-level namespace name, also known as a "vendor namespace".</li>
<li>The fully qualified class name MAY have one or more sub-namespace names.</li>
<li>The fully qualified class name MUST have a terminating class name.</li>
<li>Underscores have no special meaning in any portion of the fully qualified class name.</li>
<li>Alphabetic characters in the fully qualified class name MAY be any combination of lower case and upper case.</li>
<li>All class names MUST be referenced in a case-sensitive fashion.</li></ul>

<h3>When loading a file that corresponds to a fully qualified class name ...</h3>
<ul>
<li>A contiguous series of one or more leading namespace and sub-namespace names, not including the leading namespace separator, in the fully qualified class name (a "namespace prefix") corresponds to at least one "base directory".</li>
<li>The contiguous sub-namespace names after the "namespace prefix" correspond to a subdirectory within a "base directory", in which the namespace separators represent directory separators. The subdirectory name MUST match the case of the sub-namespace names.</li>
<li>The terminating class name corresponds to a file name ending in .php. The file name MUST match the case of the terminating class name.</li></ul>

<h3>Autoloader implementations MUST NOT throw exceptions, MUST NOT raise errors of any level, and SHOULD NOT return a value.</h3>
