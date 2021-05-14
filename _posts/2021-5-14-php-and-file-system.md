---
title: "PHP, Filesystems and File I/O"
categories:
  - Blog
tags:
  - php
---

One of the benefits of PHP being a server side scripting environment is that it gives the web developer easy access to the filesystem of the server on which the web server is running. This gives us the ability to create, open, delete, read and write to files. We can also traverse the directory hierarchy of the server systems to do things like get directory listings and create new sub-directories

<h2>Opening and Creating Files in PHP</h2>

Existing files are opened, and new files created using the PHP fopen() function. The fopen() function accepts two arguments and returns a file handle which is subsequently used for all future read and write interactions with that file. The first argument is the name (including the path) of the file to open. This path is relative to the server filesystem root, not your web server root. The second argument is an attribute indicating the mode in which to open the file (create, read only, write only etc).

<h2>Closing Files in PHP</h2>

Once a file has been opened it can be closed using the fclose() function. The fclose() function takes a single argument - the file handle returned by the fopen function when the file was first opened.

Given this information we can write a script to open a file. For the purposes of this example we will create a new file in the /tmp directory of our web server. We will open the file in w+ mode so that it will be created if it does not already exist and provide both read and write access. We will then close the file using fclose():

<code>

<?php
$fileHandle = fopen('/tmp/php_essentials.txt', 'w+')
 OR die ("Can't open file\n");

fclose ($fileHandle);
?>
</code>

<h2>Writing to a File using PHP</h2>

Having created and opened the file the next task is to write data to the file. We can do this using the PHP fwrite() and fputs() functions. These are essentially the same function so either can be used.

fwrite() takes two arguments, the file handle returned from the original fopen() call and the string to be written. We can, therefore, extend our example to write a string to our file:

<code>
<?php

$fileHandle = fopen('/tmp/php_essentials.txt', 'w+')
 OR die ("Can't open file\n");

$result = fwrite ($fileHandle, "This line of text was written by PHP\n");

if ($result)
{
     echo "Data written successfully.<br>";
} else {
     echo "Data write failed.<br>";
}

fclose($fileHandle);
?>
</code>

<h2>Reading From a File using PHP</h2>

Data can be read from a file using the PHP fread() function. fread() accepts two arguments, the file handle and the number of bytes to be read from the file:

<code>
<?php
$fileHandle = fopen('/tmp/php_essentials.txt', 'w+')
 OR die ("Can't open file\n");

fwrite ($fileHandle, "This line of text was written by PHP\n");


fclose($fileHandle);

$fileHandle = fopen('/tmp/php_essentials.txt', 'r')
 OR die ("Can't open file\n");

$fileData = fread ($fileHandle, 1024);

echo "data = $fileData";

fclose($fileHandle);

?>
</code>

<h2>Checking Whether a File Exists</h2>

The file_exists function can be used at any time to find if a file already exists in the filesystem. The function takes a single argument - the path to the file in question and returns a boolean true or false value depending on the existence of the file.

<h2>Moving, Copying and Deleting Files with PHP</h2>

Files can be copied using the copy() function, renamed using the rename() function and deleted using the unlink() function. For example we can perform a number of tasks on our example file:

<code>
<?php

if (file_exists('/tmp/php_essentials.txt)
{
	copy ('/tmp/php_essentials.txt, '/tmp/php_essentials.bak'); // Copy the file

	rename ('/tmp/php_essentials.bak', '/tmp/php_essentials.old'); // Rename the file

	unlink ('/tmp/php_essentials.old'); // Delete the file
}
?>
</code>

<h2>PHP Output Buffering</h2>

Output buffering in PHP is a mechanism whereby content that would normally be sent directly to the output stream is initially held in a buffer until the buffer is flushed. This provides control over when output is presented to the user (perhaps in situations where there is a delay in gathering some data from a database for example).

Output Buffering is initiated using the ob_start() function. ob_start() can be called with no arguments but does support three optional arguments:
<ul>
<li>callback function - specifies a user defined function to be called before the buffer is flushed</li>

<li>bytes - an integer representing the number of bytes to be buffered before the callback is triggered. Set to null to disable this feature</li>

<li>delete buffer - Boolean value specifying whether buffer should be deleted after ob_end() call.</li>
</ul>

The contents of the buffer are flushed using the ob_flush() function. It is also to possible to both flush and stop future buffering using the ob_end_flush() function.

It is also possible to delete all buffer content without flushing with a call to the ob_clean() function.

Finally the contents of the buffer may inspected at any time using the ob_get_contents() function which returns a string containing the buffer content. 