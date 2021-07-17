---
title: "Authorization in Linux"
categories:
  - Blog
tags:
  - Linux
---

Linux is a clone of UNIX, the multi-user operating system which can be accessed by many users simultaneously. Linux can also be used in mainframes and servers without any modifications. But this raises security concerns as an unsolicited or malign user can corrupt, change or remove crucial data. For effective security, Linux divides authorization into 2 levels.

<ul>
<li>Ownership</li>
<li>Permission</li>
</ul>

<h2>Ownership of Linux files</h2>

Every file and directory on your Unix/Linux system is assigned 3 types of owner, given below.

<h3>User</h3>

A user is the owner of the file. By default, the person who created a file becomes its owner. Hence, a user is also sometimes called an owner.

<h3>Group</h3>

A user- group can contain multiple users. All users belonging to a group will have the same Linux group permissions access to the file. Suppose you have a project where a number of people require access to a file. Instead of manually assigning permissions to each user, you could add all users to a group, and assign group permission to file such that only this group members and no one else can read or modify the files.

<h3>Other</h3>

Any other user who has access to a file. This person has neither created the file, nor he belongs to a usergroup who could own the file. Practically, it means everybody else. Hence, when you set the permission for others, it is also referred as set permissions for the world.

Now, the big question arises how does Linux distinguish between these three user types so that a user 'A' cannot affect a file which contains some other user 'B's' vital information/data. It is like you do not want your colleague, who works on your Linux computer, to view your images. This is where Permissions set in, and they define user behavior. 

<h2>Permissions</h2>

Every file and directory in your UNIX/Linux system has following 3 permissions defined for all the 3 owners discussed above.

<ul>
<li><b>Read</b>: This permission give you the authority to open and read a file. Read permission on a directory gives you the ability to lists its content.</li>
<li><b>Write</b>: The write permission gives you the authority to modify the contents of a file. The write permission on a directory gives you the authority to add, remove and rename files stored in the directory. Consider a scenario where you have to write permission on file but do not have write permission on the directory where the file is stored. You will be able to modify the file contents. But you will not be able to rename, move or remove the file from the directory.</li>
<li><b>Execute</b>: In Windows, an executable program usually has an extension ".exe" and which you can easily run. In Unix/Linux, you cannot run a program unless the execute permission is set. If the execute permission is not set, you might still be able to see/modify the program code(provided read & write permissions are set), but not run it.</li>
</ul>