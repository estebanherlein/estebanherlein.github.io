---
title: "Git merge types"
categories:
  - Blog
tags:
  - git
  - Version Control
---

<h2>Fast Forward Merge</h2>

A fast-forward merge can occur when there is a linear path from the current branch tip to the target branch.

Instead of “actually” merging the branches, all Git has to do to integrate the histories is move (i.e., “fast forward”) the current branch tip up to the target branch tip. 

This effectively combines the histories, since all of the commits reachable from the target branch are now available through the current one. 

For example, a fast forward merge of some-feature into master would look something like the following:

<img src="https://i.imgur.com/zBrgd9f.png" alt="git merge types example" > 

<b>However, a fast-forward merge is not possible if the branches have diverged. </b>

<h2>Three Way Merge</h2>

When there is not a linear path to the target branch, Git has no choice but to combine them via a 3-way merge. 

3-way merges use a dedicated commit to tie together the two histories. 

The nomenclature comes from the fact that Git uses three commits to generate the merge commit: the two branch tips and their common ancestor.

<img src="https://i.imgur.com/jeWmyaU.png" alt="git merge types example 2" > 

<h2> When to use each one </h2>

While you can use either of these merge strategies, many developers like to use fast-forward merges (facilitated through rebasing) for small features or bug fixes, while reserving 3-way merges for the integration of longer-running features. 

In the latter case, the resulting merge commit serves as a symbolic joining of the two branches.

<h3>Fast-forward example</h3>

Our first example demonstrates a fast-forward merge.

The code below creates a new branch, adds two commits to it, then integrates it into the main line with a fast-forward merge.

<pre> <code>
# Start a new feature
git checkout -b new-feature master
# Edit some files
git add file
git commit -m "Start a feature"
# Edit some files
git add file
git commit -m "Finish a feature"
# Merge in the new-feature branch
git checkout master
git merge new-feature
git branch -d new-feature
</code></pre>

This is a common workflow for short-lived topic branches that are used more as an isolated development than an organizational tool for longer-running features.

Also note that Git should not complain about the git branch -d, since new-feature is now accessible from the master branch.

In the event that you require a merge commit during a fast forward merge for record keeping purposes you can execute git merge with the --no-ff option.

<pre> <code>
git merge --no-ff branch
</code></pre>

This command merges the specified branch into the current branch, but always generates a merge commit (even if it was a fast-forward merge). 

This is useful for documenting all merges that occur in your repository.

<h3>3-way merge example</h3>

The next example is very similar, but requires a 3-way merge because master progresses while the feature is in-progress. 

This is a common scenario for large features or when several developers are working on a project simultaneously.

<pre> <code>
Start a new feature
git checkout -b new-feature master
# Edit some files
git add file
git commit -m "Start a feature"
# Edit some files
git add file
git commit -m "Finish a feature"
# Develop the master branch
git checkout master
# Edit some files
git add file
git commit -m "Make some super-stable changes to master"
# Merge in the new-feature branch
git merge new-feature
git branch -d new-feature
</code></pre>

Note that it’s impossible for Git to perform a fast-forward merge, as there is no way to move master up to new-feature without backtracking.

For most workflows, new-feature would be a much larger feature that took a long time to develop, which would be why new commits would appear on master in the meantime. 

If your feature branch was actually as small as the one in the above example, you would probably be better off rebasing it onto master and doing a fast-forward merge. This prevents superfluous merge commits from cluttering up the project history.

<h2>Resolving conflict</h2>

If the two branches you're trying to merge both changed the same part of the same file, Git won't be able to figure out which version to use. When such a situation occurs, it stops right before the merge commit so that you can resolve the conflicts manually.

The great part of Git's merging process is that it uses the familiar edit/stage/commit workflow to resolve merge conflicts.

When you encounter a merge conflict, running the git status command shows you which files need to be resolved. 

For example, if both branches modified the same section of hello.py, you would see something like the following:

<pre><code>
On branch master
Unmerged paths:
(use "git add/rm ..." as appropriate to mark resolution)
both modified: hello.py
</code></pre>


<h2>Key take-aways</h2>

<ul>
<li>Git merging combines sequences of commits into one unified history of commits.</li>
<li>There are two main ways Git will merge: Fast Forward and Three way</li>
<li>Git can automatically merge commits unless there are changes that conflict in both commit sequences.</li>
</ul>
