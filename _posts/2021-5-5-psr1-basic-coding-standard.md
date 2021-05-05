---
title: "PSR-1: Basic Coding Standard "
categories:
  - Blog
tags:
  - php
---

The first standard is the basic coding standard. These are the basic rules that the voting members of the Framework Interoperability Group feel that you should follow when coding PHP.

Surprisingly, the list is not too long (some coding standards for C/C++ are books unto themselves), but never fear, there’s more in PSR-12. 

<h2>Guideline</h2>

<ul>
<li>Files MUST use only <?php and <?= tags.</li>
<li>Files MUST use only UTF-8 without BOM for PHP code.</li>
<li>Files SHOULD either declare symbols (classes, functions, constants, etc.) or cause side-effects (e.g. generate output, change .ini settings, etc.) but SHOULD NOT do both.</li>
<li>Namespaces and classes MUST follow an "autoloading" PSR: [PSR-0, PSR-4].</li>
<li>Class names MUST be declared in StudlyCaps.</li>
<li>Class constants MUST be declared in all upper case with underscore separators.</li>
<li>Method names MUST be declared in camelCase.</li>
</ul>

<h3>PHP Tags</h3>

PHP code MUST use the long <?php ?> tags or the short-echo <?= ?> tags; it MUST NOT use the other tag variations.

<h3>Character Encoding</h3>

PHP code MUST use only UTF-8 without BOM.

<h3>Side Effects</h3>

A file SHOULD declare new symbols (classes, functions, constants, etc.) and cause no other side effects, or it SHOULD execute logic with side effects, but SHOULD NOT do both.

The phrase "side effects" means execution of logic not directly related to declaring classes, functions, constants, etc., merely from including the file.

"Side effects" include but are not limited to: generating output, explicit use of require or include, connecting to external services, modifying ini settings, emitting errors or exceptions, modifying global or static variables, reading from or writing to a file, and so on.

<h3>Namespace and Class Names</h3>

Namespaces and classes MUST follow an "autoloading" PSR: [PSR-0, PSR-4].

This means each class is in a file by itself, and is in a namespace of at least one level: a top-level vendor name.

Class names MUST be declared in StudlyCaps.

Code written for PHP 5.3 and after MUST use formal namespaces.

<h3>Constants</h3>

Class constants MUST be declared in all upper case with underscore separators.

<h3>Methods</h3>

Method names MUST be declared in camelCase()