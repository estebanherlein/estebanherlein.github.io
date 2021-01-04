---
title: "Bash Scripting"
categories:
  - Blog
tags:
  - Linux
  - Shell essentials
  - Dev-ops
---
 
You can build scripts to automate repetitive parts of your work, which frees your time and ensures consistency each time you use the script. For instance, if you run the same five commands every day, you can turn them into a shell script that reduces your work to one command.
 
<h2> Shell Scripts</h2>
 
A shell script is a file of executable commands that has been stored in a text file. When the file is run, each command is executed. Shell scripts have access to all the commands of the shell, including logic. 
 
A script can therefore test for the presence of a file or look for particular output and change its behavior accordingly.

There are various shells with their own language syntax. Therefore, more complicated scripts will indicate a particular shell by specifying the absolute path to the interpreter as the first line, prefixed by #! 


<pre>
<code>
#!/bin/sh
echo “Hello, World!”
</code>
</pre>
or 
<pre>
<code>
#!/bin/bash
echo “Hello, World!”
</code>
</pre>

The two characters #! are traditionally called the hash and the bang respectively, which leads to the shortened form of “shebang” when they’re used at the beginning of a script.

Incidentally, the shebang (or crunchbang) is used for traditional shell scripts and other text-based languages like Perl, Ruby, and Python. Any text file marked as executable will be run under the interpreter specified in the first line as long as the script is run directly. If the script is invoked directly as an argument to an interpreter, such as sh script or bash script, the given shell will be used no matter what’s in the shebang line.


<h2>Basics</h2>
<h3>Variables</h3>

Variables are a key part of any programming language. 

A very simple use of variables can be seen here.

<pre>
<code>
#!/bin/bash
ANIMAL="penguin"
echo "My favorite animal is a $ANIMAL"
</code>
</pre>

After the shebang line is a directive to assign some text to a variable. The variable name is ANIMAL and the equals sign assigns the string penguin. 

It is important that there are no spaces between the name of the variable, the equals sign, and the item to be assigned to the variable. If you have a space there, you will get an odd error such as “command not found”. Capitalizing the name of the variable is not necessary but it is a useful convention to separate variables from commands to be executed.

Next, the script echos a string to the console. The string contains the name of the variable preceded by a dollar sign. When the interpreter sees that dollar sign it recognizes that it will be substituting the contents of the variable, which is called interpolation. The output of the script is then My favorite animal is a penguin.


Another way to assign to a variable is to use the output of another command as the contents of the variable by enclosing the command in back ticks:

<pre>
<code>
#!/bin/bash
CURRENT_DIRECTORY=`pwd`
echo "You are in $CURRENT_DIRECTORY"
</code>
</pre>


It is possible to get input from the user of your script and assign it to a variable through the read command:

<pre>
<code>
#!/bin/bash

echo -n "What is your name? "
read NAME
echo "Hello $NAME!"
</code>
</pre>

There are some special variables in addition to the ones you set. You can pass arguments to your script:

<pre>
<code>
#!/bin/bash
echo "Hello $1"
</code>
</pre>
A dollar $ sign followed by a number N corresponds to the Nth argument passed to the script.

<h3>Conditionals</h3>

A basic if statement looks like this:

<pre>
<code>
if somecommand; then
  # do this if somecommand has an exit code of 0
fi
</code>
</pre>

The next example will run “somecommand” (actually, everything up to the semicolon) and if the exit code is 0 then the contents up until the closing fi will be run. Using what you know about grep, you can now write a script that does different things based on the presence of a string in the password file:

<pre>
<code>
#!/bin/bash

if grep -q root /etc/passwd; then
  echo root is in the password file
else
  echo root is missing from the password file
fi
</code>
</pre>


The if statement has a final form that lets you do multiple comparisons at one time using elif (short for else if).

<pre>
<code>
#!/bin/bash

if [ "$1" = "hello" ]; then
  echo "hello yourself"
elif [ "$1" = "goodbye" ]; then
  echo "nice to have met you"
  echo "I hope to see you again"
else
  echo "I didn't understand that"
fi
</code>
</pre>

The if/elif/else tests can become quite verbose and complicated. The case statement provides a different way of making multiple tests easier.

<pre>
<code>
#!/bin/bash

case "$1" in
hello|hi)
  echo "hello yourself"
  ;;
goodbye)
  echo "nice to have met you"
  echo "I hope to see you again"
  ;;
*)
  echo "I didn't understand that"
esac
</code>
</pre>

The * pattern is the same as an else because it matches anything. The behavior of the case statement is similar to the if/elif/else statement in that processing stops after the first match. If none of the other options matched, the * ensures that the last one will match.

<h3>Loops</h3>

Loops allow code to be executed repeatedly. They can be useful in numerous situations, such as when you want to run the same commands over each file in a directory, or repeat some action 100 times. There are two main loops in shell scripts: the for loop and the while loop.

for loops are used when you have a finite collection over which you want to iterate, such as a list of files, or a list of server names:

<pre>
<code>
#!/bin/bash

SERVERS="servera serverb serverc"
for S in $SERVERS; do
  echo "Doing something to $S"
done
</code>
</pre>

The script first sets a variable containing a space separated list of server names. The for statement then loops over the list of servers, each time it sets the S variable to the current server name. 

The choice of S was arbitrary, but note that the S has no dollar sign but the $SERVERS does, showing that $SERVERS will be expanded to the list of servers. The list does not have to be a variable. 

This example shows two more ways to pass a list.
<pre>
<code>
#!/bin/bash

for NAME in Sean Jon Isaac David; do
  echo "Hello $NAME"
done

for S in *; do
  echo "Doing something to $S"
done
</code>
</pre>

The first loop is functionally the same as the previous example, except that the list is passed to the for loop directly instead of using a variable. Using a variable helps the clarity of the script as someone can easily make changes to the variable rather than looking at a loop.

The second loop uses a * which is a file glob. This gets expanded by the shell to all the files in the current directory.

The other type of loop, a while loop, operates on a list of unknown size. Its job is to keep running and on each iteration perform a test to see if it should run another time. You can think of it as “while some condition is true, do stuff.”

<pre>
<code>
#!/bin/bash

i=0
while [ $i -lt 10 ]; do
  echo $i
  i=$(( $i + 1))
done
echo “Done counting”
</code>
</pre>

The example above shows a while loop that counts from 0 to 9. A counter variable, i, is initialized to 0. Then a while loop is run with the test being “is $i less than 10?” Note that the while loop uses the same notation as an if statement!

Within the while loop the current value of i is echoed and then 1 is added to it through the $(( arithmetic )) command and assigned back into i. Once i becomes 10 the while statement returns false and processing continues after the loop.