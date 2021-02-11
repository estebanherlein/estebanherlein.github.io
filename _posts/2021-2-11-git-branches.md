---
title: "Git branches"
categories:
  - Blog
tags:
  - git
  - Version control
---


Branching means you diverge from the main line of development and continue to do work without messing with that main line. 

In many VCS tools, this is a somewhat expensive process, often requiring you to create a new copy of your source code directory, which can take a long time for large projects.

Some people refer to Git’s branching model as its “killer feature,” and it certainly sets Git apart in the VCS community. 

Why is it so special? The way Git branches is incredibly lightweight, making branching operations nearly instantaneous, and switching back and forth between branches generally just as fast. 

Unlike many other VCSs, Git encourages workflows that branch and merge often, even multiple times in a day. Understanding and mastering this feature gives you a powerful and unique tool and can entirely change the way that you develop.


<h2>How Git stores its data.</h2>

Git doesn’t store data as a series of changesets or differences, but instead as a series of snapshots.
 
When you make a commit, Git stores a commit object that contains a pointer to the snapshot of the content you staged. 

This object also contains the author’s name and email address, the message that you typed, and pointers to the commit or commits that directly came before this commit (its parent or parents): zero parents for the initial commit, one parent for a normal commit, and multiple parents for a commit that results from a merge of two or more branches.

To visualize this, let’s assume that you have a directory containing three files, and you stage them all and commit. 

Staging the files computes a checksum for each one (the SHA-1 hash we mentioned in What is Git?), stores that version of the file in the Git repository (Git refers to them as blobs), and adds that checksum to the staging area

When you create the commit by running git commit, Git checksums each subdirectory (in this case, just the root project directory) and stores them as a tree object in the Git repository.

Git then creates a commit object that has the metadata and a pointer to the root project tree so it can re-create that snapshot when needed.

Your Git repository now contains five objects: three blobs (each representing the contents of one of the three files), one tree that lists the contents of the directory and specifies which file names are stored as which blobs, and one commit with the pointer to that root tree and all the commit metadata.

<img src="https://i.imgur.com/pJ1qMEE.png" alt="git data store example" > 
 
 If you make some changes and commit again, the next commit stores a pointer to the commit that came immediately before it.
 
<img src="https://i.imgur.com/mdFVpzz.png" alt="git data store example 2" > 

<h2> What's a Git branch</h2>

A branch in Git is simply a lightweight movable pointer to one of these commits. 

The default branch name in Git is master. 

As you start making commits, you’re given a master branch that points to the last commit you made. Every time you commit, the master branch pointer moves forward automatically

<h2> What happens when you create a new branch?</h2>

Well, doing so creates a new pointer for you to move around. 

Let’s say you want to create a new branch called testing. 

<pre><code>git branch testing</code></pre>

This creates a new pointer to the same commit you’re currently on.

<img src="https://i.imgur.com/8GZAn0Y.png" alt="git branch example" > 

Git keeps a special pointer called HEAD.

This is a pointer to the local branch you’re currently on. In this case, you’re still on master. 

The git branch command only created a new branch, it didn’t switch to that branch.

You can easily see this by running a simple git log command that shows you where the branch pointers are pointing. This option is called --decorate.

<pre><code>git log --oneline --decorate</code></pre>


<h2>Switching Branches</h2>

To switch to an existing branch, you run the git checkout command. 

<pre><code>git checkout testing</code></pre>

This moves HEAD to point to the testing branch.

What is the significance of that?

Well, let’s do another commit.
 
This is interesting, because now your testing branch has moved forward, but your master branch still points to the commit you were on when you ran git checkout to switch branches. 

Let’s switch back to the master branch

<pre><code>git checkout master</code></pre>

That command did two things.

It moved the HEAD pointer back to point to the master branch, and it reverted the files in your working directory back to the snapshot that master points to. 

This also means the changes you make from this point forward will diverge from an older version of the project. 

It essentially rewinds the work you’ve done in your testing branch so you can go in a different direction.

Let’s make a few changes and commit again.

Now your project history has diverged. 

You created and switched to a branch, did some work on it, and then switched back to your main branch and did other work. 

Both of those changes are isolated in separate branches: you can switch back and forth between the branches and merge them together when you’re ready.

And you did all that with simple branch, checkout, and commit commands.

<h2>Why is branching in Git such a commmon practice?</h2>

Because a branch in Git is actually a simple file that contains the 40 character SHA-1 checksum of the commit it points to, branches are cheap to create and destroy. 

Creating a new branch is as quick and simple as writing 41 bytes to a file (40 characters and a newline).

Also, because we’re recording the parents when we commit, finding a proper merge base for merging is automatically done for us and is generally very easy to do. 

These features help encourage developers to create and use branches often.