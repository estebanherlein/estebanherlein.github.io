---
title: "Fish Shell"
categories:
  - Blog
tags:
  - Linux
  - Shell essentials
---

Friendly interactive shell (abbreviated as fish) is the name of a Unix shell that is intended to be interactive and user-friendly, unlike other shells.

The design goal of fish is to give the user a diverse set of powerful features in a way that is easy to discover, remember, and use.

fish is considered an "exotic shell", as its syntax is not derived from a Bourne shell (Ksh, bash, zsh) or some C shell (csh, tcsh).

Also, unlike other shells, which disable some features to take care of system resources, fish enables all features by default. 

fish includes features like syntax highlighting, autosuggest-as-you-type, and fancy tab completions that just work, with no configuration required.

<h2>Syntax highlighting</h2>

fish interprets the command line as it is typed and uses syntax highlighting to provide feedback to the user. The most important feedback is the detection of potential errors. By default, errors are marked red.

Detected errors include:
<ul>
<li>Non existing commands.</li>
<li>Reading from or appending to a non existing file.</li>
<li>Incorrect use of output redirects</li>
<li>Mismatched parenthesis</li>
</ul>

When the cursor is over a parenthesis or a quote, fish also highlights its matching quote or parenthesis.


<h2>Automatic suggestions</h2>

fish suggests commands as you type, based on command history, completions, and valid file paths. 

As you type commands, you will see a suggestion offered after the cursor, in a muted gray color (which can be changed with the fish_color_autosuggestion variable).

To accept the autosuggestion (replacing the command line contents), press right arrow or Control+F. To accept the first suggested word, press Alt+→,Right or Alt+F. If the autosuggestion is not what you want, just ignore it: it won't execute unless you accept it.

Autosuggestions are a powerful way to quickly summon frequently entered commands, by typing the first few characters. They are also an efficient technique for navigating through directory hierarchies.

<h2>Tab Completion</h2>

Tab completion is one of the most time saving features of any modern shell.

By tapping the tab key, the user asks fish to guess the rest of the command or parameter that the user is currently typing. 

If fish can only find one possible completion, fish will write it out. 

If there is more than one completion, fish will write out the longest prefix that all completions have in common. 

If the completions differ on the first character, a list of all possible completions is printed. 

The list features descriptions of the completions and if the list doesn't fit the screen, it is scrollable by using the arrow keys, the page up/page down keys, the tab key or the space bar.

These are the general purpose tab completions that fish provides:
<ul>
<li>Completion of commands (builtins, functions and regular programs).</li>
<li>Completion of shell variable names.</li>
<li>Completion of usernames for tilde expansion.</li>
<li>Completion of filenames, even on strings with wildcards such as '*' and '**'.</li>
</ul>

<h2>Web-based configuration</h2>

You are able to configure  colors, change the Fish indicator and view functions, variables, history, key links, all from a web page.

To start the web configuration interface, you will simply have to type: 

<pre><code>fish_config</code></pre>


<h2>Getting help</h2>

To open the Fish documentation page in our default web browser from the terminal, simply type: 

<pre><code>help</code></pre>