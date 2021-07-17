---
title: "Glob characters"
categories:
  - Blog
tags:
  - Linux
  - Shell Essentials
---


Bash does not support native regular expressions like some other standard programming languages. 

The Bash shell feature that is used for matching or expanding specific types of patterns is called globbing. 


Globbing is mainly used to match filenames or searching for content in a file. 

Globbing uses wildcard characters to create the pattern. The most common wildcard characters that are used for creating globbing patterns are described below.


<h2>Asterisk</h2>

The asterisk '*' character is used to represent zero or more of any character in a filename. For example, to display all of the files in the /etc directory that begin with the letter t:

> sysadmin@localhost:~$ echo /etc/t*   

The pattern t* matches any file in the /etc directory that begins with the character t followed by zero or more of any character. In other words, any files that begin with the letter t.

You can use the asterisk character at any place within the filename pattern. For example, the following matches any filename in the /etc directory that ends with .d:

> sysadmin@localhost:~$ echo /etc/*.d                                    

In the next example, all of the files in the /etc directory that begin with the letter r and end with .conf are displayed:

> sysadmin@localhost:~$ echo /etc/r*.conf         

<h2> Question mark</h2>

The question mark ? character represents any single character. Each question mark character matches exactly one character, no more and no less.

Suppose you want to display all of the files in the /etc directory that begin with the letter t and have exactly 7 characters after the t character:

> sysadmin@localhost:~$ echo /etc/t???????     

Glob characters can be used together to find even more complex patterns. The pattern /etc/*???????????????????? command only matches files in the /etc directory with twenty or more characters in the filename:

> sysadmin@localhost:~$ echo /etc/*????????????????????                  

The asterisk and question mark could also be used together to look for files with three-letter extensions by using the /etc/*.??? pattern:

> sysadmin@localhost:~$ echo /etc/*.???    

<h2>Bracket [ ] Characters</h2>

The bracket [] characters are used to match a single character by representing a range of characters that are possible match characters. For example, the /etc/[gu]* pattern matches any file that begins with either a g or u character and contains zero or more additional characters:

> sysadmin@localhost:~$ echo /etc/[gu]*                

Brackets can also be used to a represent a range of characters. For example, the /etc/[a-d]* pattern matches all files that begin with any letter between and including a and d:

> sysadmin@localhost:~$ echo /etc/[a-d]*

The /etc/*[0-9]* pattern displays any file that contains at least one number:

> sysadmin@localhost:~$ echo /etc/*[0-9]*

<h2>Exclamation Point ! Character </h2>

The exclamation point ! character is used in conjunction with the square brackets to negate a range. For example, the pattern /etc/[!DP]* matches any file that does not begin with a D or P.

> sysadmin@localhost:~$ echo /etc/[!a-t]*

