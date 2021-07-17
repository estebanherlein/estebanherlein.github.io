---
title: "Navigating the filesystem"
categories:
  - Blog
tags:
  - Linux
  - Shell Essentials
---

In Linux, everything is considered a file.

Files are used to store data such as text, graphics, and programs. 

Directories are a type of file used to store other files; Windows and Mac OS X users typically refer to them as folders. 

In any case, directories are used to provide a hierarchical organization structure. However, this structure may be somewhat different depending on the type of system in use.

When working in a Linux operating system, it is important to know how to manipulate files and directories. Some Linux distributions have GUI-based applications that allow you to manage files, but it is advantageous to know how to perform these operations via the command line

<h1>Directory Structure</h1>

On a Windows system, the top level of the directory structure is called My Computer. Physical devices, such as hard drives, USB drives, network drives, show up under My Computer and are each assigned a drive letter, such as C: or D:.

Like Windows, the Linux directory structure, typically called a filesystem, also has a top level. However instead of My Computer, it is called the root directory, and it is symbolized by the slash / character. Additionally, there are no drives in Linux; each physical device is accessible under a directory, as opposed to a drive letter.

<h2> Home Directory</h2>

To begin with, on most Linux distributions there is a directory called home under the root / directory.

Under this /home directory there is a directory for each user on the system. The directory name is the same as the name of the user, so a user named sysadmin would have a home directory called /home/sysadmin.

The home directory is an important directory. To begin with, when a user opens a shell, they should automatically be placed in their home directory, as typically this is where they do most of their work.

Additionally, the home directory is one of the few directories where the user has full control to create and delete additional files and directories. On most Linux distributions, the only users who can access the files in a home directory are the owner and the administrator on the system. Most other directories in a Linux filesystem are protected with file permissions.

The home directory has a special symbol used to represent it; the tilde ~ character. So if the sysadmin user is logged in, the tilde ~ character can be used in place of the /home/sysadmin directory.

It is also possible to refer to another user's home directory by using the tilde ~ character followed by the name of the user account. For example, ~bob would be the equivalent of /home/bob.

<h2>Paths</h2>

A path is a list of directories separated by the / character. If you think of the filesystem as a map, paths are the directory addresses, which include step-by-step navigation directions; they can be used to indicate the location of any file within the filesystem.

For example, /home/sysadmin is a path to the home directory:

There are two types of paths: absolute and relative.

<h3>Absolute paths</h3>

They allow the user to specify the exact location of a directory.

It always starts at the root directory, and therefore it always begins with the / character. The path /home/sysadmin is an absolute path; it tells the system to begin at the root / directory, move into the home directory, and then into the sysadmin directory.

<h3>Relative paths</h3> 

They start from the current directory. 

A relative path gives directions to a file relative to the current location in the filesystem. They do not start with the / character. Instead, they start with the name of a directory. More specifically, relative paths start with the name of a directory contained within the current directory.

<h2> Long Display Listing </h2>

Each file has details associated with it called metadata. This can include information such as the size, ownership, or timestamps. To view this information, use the -l option to the ls command. Below, a listing of the /var/log directory is used as an example, since it provides a variety of output:

 <img src="https://i.imgur.com/O55DN0Q.png" alt="console output" > 
 
 In the output above, each line displays metadata about a single file. The following describes each of the fields of data in the output of the ls -l command:
 
 <h3>File type</h3>
 
> <b>-</b>rw-r--r-- 1 root   root  15322 Dec 10 21:33 alternatives.log                   
> <b>d</b>rwxr-xr-x 1 root   root   4096 Jul 19 06:52 apt 

The first character of each line indicates the type of file. The file types are:

<img src="https://i.imgur.com/IYEOwFg.png" alt="file type table" > 

The first file alternatives.log is a regular file (-), while the second file apt is a directory (d).

<h3>Permissions</h3>

> d<b>rwxr-xr-x</b> 2 root   root   4096 Jul 19 06:51 journal

The next nine characters demonstrate the permissions of the file. Permissions indicate how certain users can access a file. 


<h3>Hard Link Count</h3>

> -rw-r----- <b>1</b> syslog adm     371 Dec 15 16:38 auth.log
> drwxr-xr-x <b>2</b> root   root   4096 Jul 19 06:51 journal

This number indicates how many hard links point to this file. 

<h3>User Owner</h3>


> -rw-r----- 1 <b>syslog</b> adm     197 Dec 15 16:38 cron.log

Every file is owned by a user account. This is important because the owner has the rights to set permissions on a file. 


<h3>Group Owner</h3>


> -rw-rw-r-- 1 root  <b>utmp</b>  292584 Dec 15 16:38 lastlog

Indicates which group owns this file. This is important because any member of this group has a set of permissions on the file.

<h3>File Size</h3>

Displays the size of the file in bytes.

> -rw-r----- 1 syslog adm   <b>14185</b> Dec 15 16:38 syslog

For directories, this value does not describe the total size of the directory, but rather how many bytes are reserved to keep track of the filenames in the directory. In other words, ignore this field for directories.

<h3>Timestamp</h3>

> -rw-rw---- 1 root   utmp      0 <b>May 26  2018</b> btmp  

Indicates the time that the file's contents were last modified. For directories, this timestamp indicates the last time a file was added or deleted from the directory.

<h3>File Name</h3>


> -rw-r--r-- 1 root   root  35330 May 26  2018 <b>bootstrap.log</b>

The final field contains the name of the file or directory.



