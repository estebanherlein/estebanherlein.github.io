---
title: "Git file lifecycle"
categories:
  - Blog
tags:
  - git
  - Version Control
---



When a project is under Git version control system, they are present in three major Git states .


<ul>
<li>Working directory </li>
<li>Staging area </li>
<li>Git directory </li>
</ul>

These stages are the essence of Git. You get great flexibility in tracking the files due to these stages that files can reside in. 

Let’s understand each of these states one by one


<h2>Working Directory</h2>

Consider a project residing in your local system. This project may or may not be tracked by Git. In either case, this project directory is called your Working directory.

Working directory is the directory containing hidden .git folder.

For sake of further discussion, let’s assume that this directory is now tracked by Git.

That is we’ve created a Git repository in this existing project directory. 

So, as discussed in the tutorial on Creation of Git Repository, a hidden .git folder is initialized therein. 

In this state, Git is just aware of the files in the project. It doesn’t track the files yet. 

To track the files, we’ve to commit these files by first adding the files to the staging area. This brings us to the next state in Git life-cycle.

<h2>Staging Area</h2>

While we’re in the working directory, we select the files that have to be tracked by Git. 

Why do we need to this? Why don’t we track everything in the project? That’s because some files in the project like class files, log files, result files and temporary data files are dynamically generated. 

It doesn’t make sense to track the versions of these files. Whereas the source code files, data files, configuration files and other project artifacts contain the business logic of the application. These files are to be tracked by Git are thus needs to be added to the staging area.

In other words, staging area is the playground where you group, add and organize the files to be committed to Git for tracking their versions.

It’s important to make a quick note of the term called indexing here. Indexing is the process of adding files to the staging area. In other words, index constitutes of files added to the staging area.

<h2>Git Directory</h2>

Now that the files to be committed are grouped and ready in the staging area, we can commit these files. 

So, we commit this group of files along with a commit message explaining what is the commit about.

Apart from commit message, this step also records the author and time of the commit. 

Now, a snapshot of the files in the commit is recorded by Git. The information related to this commit (names of files committed, date and time of commit, author of commit, commit message) is stored in the Git directory.

Thus, Git directory is the database where metadata about project files’ history will be tracked.

<h2>Additional Lifecycle Stage with Github</h2>

Now mind that we’re learning the lifecycle in Git exclusively. 

That is, it’s important to note that the three stages discussed above are only for Git and not Github. 

Why? Because you can track versions of your files by using only Git. 

Github is needed when you want to collaborate and publish your code to a team or community. Thus, it helps to remember that the Git cycle doesn’t conventionally involve Github.

However, we work in teams and collaborate with multiple people on a given project. 

This makes it imperative to understand the additional stage related to Github. While dealing with Github, there’s a concept of Remote repository and a related process called Pushing the files.

After committing the code to the local Git repository, it has to be pushed to remote repository. 

Here, Remote repository means mirror or clone of the local Git repository in Github. 

And pushing means uploading the commits from local Git repository to remote repository hosted in Github. 

This will allow other collaborators to view the code. Thus, whatever changes you make in the local Git repository will be visible to other collaborators when you push your code to the remote repository. 