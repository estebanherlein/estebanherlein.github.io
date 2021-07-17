---
title: "Git reset"
categories:
  - Blog
tags:
  - Dev-ops
  - Version Control
  - git
---

The git reset command is a complex and versatile tool for undoing changes. It is invoked mainly in three different ways, corresponding to the command line arguments --soft, --mixed, and --hard.

Each of the three arguments corresponds to Git's three internal state management mechanisms: the commit tree (HEAD), the staging environment index, and the working directory.
 
To properly understand how to use git reset, we first have to understand Git's internal state management systems. These mechanisms are sometimes called the "three trees" of Git. This may be a misnomer, as they are not strictly traditional tree-like data structures. 

However, they are node-based and pointer-based data structures that Git uses to monitor an edit schedule. The best way to demonstrate these mechanisms is to create a changeset in a repository and follow it through all three trees.

<h2>How it works</h2>

On the surface level, git reset behaves similar to git checkout. 

While git checkout only operates on the HEAD reference pointer, git reset will move the HEAD reference pointer and the current branch reference pointer. To better demonstrate this behavior, we are going to analyze an example:

For example, a sequence of commits on the master branch. The HEAD reference and the master branch reference currently point to commit d. Now we are going to run and compare both git checkout b and git reset b.

With git checkout, the master reference still points to d. The HEAD reference has been moved and now points to commit b. The repository is now in a "detached HEAD" state.

In comparison, git reset moves both the HEAD and branch references to the specified commit.

In addition to updating the commit reference pointers, git reset will modify the state of the three trees. The reference pointer modification always happens and is an update of the third tree, the commit tree. The command-line arguments --soft, --mixed, and --hard indicate how to modify the index trees in the staging environment and in the working directory.

<h2>Main options</h2>

The default invocation of git reset has implicit arguments of --mixed and HEAD. This means that running git reset is equivalent to running git reset --mixed HEAD. Thus, HEAD is the specified commit. Instead of HEAD, you can use any Git SHA-1 commit hash.

<h3>--hard</h3>

This is the most direct, DANGEROUS and common option. When --hard is passed, the commit history reference pointers are updated to the specified commit. The staging environment index and working directory are then reset to reflect the specified commit. All previous pending changes to the staging environment index and working directory are reset to reflect the state of the commit tree. This means that any pending work left in the staging environment index and working directory will be lost.

<h3>--mixed</h3>

This is the default mode of operation. Reference pointers are updated. The staging environment index is reset to the state of the specified commit. All changes that have been undone to the staging environment index are moved to the working directory.

<h3>--soft</h3>

When the --soft argument is passed, the reference pointers are updated and the reset stops there. The staging environment index and working directory remain intact.