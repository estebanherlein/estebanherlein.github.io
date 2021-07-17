---
title: "Merge conflicts"
categories:
  - Blog
tags:
  - Dev-ops
  - Version Control
  - git
---

A merge conflict is an event that takes place when Git is unable to automatically resolve differences in code between two commits. Git can merge the changes automatically only if the commits are on different lines or branches.

Let’s assume there are two developers: Developer A and Developer B. Both of them pull the same code file from the remote repository and try to make various amendments in that file. After making the changes, Developer A pushes the file back to the remote repository from his local repository. Now, when Developer B tries to push that file after making the changes from his end, he is unable to do so, as the file has already been changed in the remote repository.

To prevent such conflicts, developers work in separate isolated branches. The Git merge command combines separate branches and resolves any conflicting edits.

<h2>Types of Git Merge Conflicts </h2>

There are two points when a merge can enter a conflicted state:

<h3>Starting the Merge Process </h3>

If there are changes in the working directory’s stage area for the current project, merging won’t start. 

In this case, conflicts happen due to pending changes that need to be stabilized using different Git commands.

<h3>During the Merge Process</h3>

The failure during the merge process indicates that there is a conflict between the local branch and the branch being merged.

In this case, Git resolves as much as possible, but there are things that have to be resolved manually in the conflicted files.

<h2>How to Resolve Merge Conflicts in Git?</h2>

There are a few steps that could reduce the steps needed to resolve merge conflicts in Git.

<ol>
<li>The easiest way to resolve a conflicted file is to open it and make any necessary changes</li>
<li>After editing the file, we can use the git add a command to stage the new merged content</li>
<li>The final step is to create a new commit with the help of the git commit command</li>
<li>Git will create a new merge commit to finalize the merge</li>
<ol>

