---
title: "Git merge"
categories:
  - Blog
tags:
  - git
  - Version Control
---

Merge is Git's way of rejoining a forked history. 

The git merge command allows you to take the independent lines of development created by branching and integrate them into a single branch.

Note that all the commands presented below are merged into the current branch.

The current branch will be updated to reflect the merge, but the target branch will not be affected at all. 

Again, this means that git merge is often used in conjunction with git checkout to select the current branch and git branch -d to remove the deprecated target branch. 

<h2>How does it work </h2>

git merge will combine multiple commit sequences into a unified history. 

In the most common use cases, git merge is used to combine two branches.

The following examples  will focus on this pattern of branch fusion. 
 
In these cases, git merge takes two commit pointers, usually the ends of the branch, and finds a common base commit between them. 

After Git finds a base commit, it creates a new "merge commit" that combines the changes from each queued merge commit sequence.

Suppose we have a new functionality branch that is based on the master branch. 

Now, we want to merge that branch of functionality with the master. 

<img src="https://i.imgur.com/0OTWLR8.png" alt="git merge example" > 

By invoking this command, the specified functionality branch will be merged with the current branch, which we will assume to be the master. 

Git will determine the merge algorithm for you.

<img src="https://i.imgur.com/UxC4fu3.png" alt="git merge example 2" > 

Merge commits are unique from other commits in that they have two main commits. 

When creating a merge commit, Git will automatically attempt to merge the separate histories.

However, if you find data that has been changed in both records, you will not be able to combine them that way. 

In that case, a version control conflict is created and Git will request user intervention in order to continue. 

<h2>Before the merge</h2>

Before running a fusion, there are a couple of preparatory steps to go through to ensure the fusion goes smoothly.

<h3>Confirmation of the receiving branch</h3>

Run git status to make sure HEAD points to the correct merge-receive branch.

If necessary, run git checkout to switch to the receiving branch. In our case, we will run git checkout master.
 
<h3>Retrieval of the last remote commits</h3>

Make sure the receiving branch and the merging branch are up to date with the latest remote changes.

Run git fetch to extract the latest remote commits. Once the recovery is complete, make sure the master branch has the latest updates by running the git pull command.

<h2>Fusion</h2>

After adopting the "prepare for merge" steps discussed above, it is possible to initiate a merge by running git merge. 
