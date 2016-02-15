# Git for Humans

## Quick reference to all commands within the book
Name | Command | Usage
--- | --- | ---
checkout | `git checkout` | Use to switch over to a branch, or to roll back to a particular commit.


A summary of each chapter of the book.

### Contents
1. Chapter 1: Thinking in Versions
2. Chapter 2: Basics
3. Chapter 3: Branches
4. Chapter 4: Remotes
5. Chapter 5: History

## Chapter 1: Thinking in Versions

Version control is a practice as much as it is a tool we use.

Git keeps a copy of every version of a project inside a **repository**. Versions are **committed** to the repo in logical steps. Commits are organised into **branches**, with a master branch that represents the offical, primary version. Commits can be thought of as _significant changes_.

Git was invented by Linus Torvalds to help with the Linux project. Git is designed to be decentralised. This means there is not just one source of the code base, but many sources. Each developer works on their own local copy of a project.

Although only one copy of each file is visible in a working folder, Git is storing copies of the same file over and over, at each different state that has been committed.

Git makes very little attempt to explain its system through metaphors, such as the way OS X uses folder icons to denote directories. It is very logical and will not do more that what you tell it to do.

> Git has more than seventy-five command-line functions, every single one of which has a specific job, with specific inputs and expected results.

### Personal notes

Git is different from the Dropbox style of version control. Dropbox automatically retains a copy of a file every time it is saved, but only keeps five of the most recent copies. Git, on the other hand, does not do this automatically and waits for you to decide when a copy should be saved. It does, however, retain every single copy that you commit.

## Chapter 2: Basics

### Using Git for the first time.

If you open up the Terminal app on a Mac, and type `git`, your Mac will prompt you to install the Apple Command Line Tools, which includes Git.

### Some basic shell commands

These are not specific to Git but are useful for navigating around folders on the command line.

`pwd` (print working directory) will display your current location as an absolute path.  
Example of a path: `/Volumes/Macintosh HD/Users/Angus/dev`.

`cd` (change directory) is used in conjunction with a path name to navigate through folders.  
Example: `cd ../images` would move back up out of the current folder and then down into a folder called _images_.

`mkdir` (make directory) will create a new folder  
Example: `mkdir css` will make a new folder, in the current location, called _css_.

`ls` (list) will show a list of all items within the current location.

All the tasks above can be done by using the Finder window instead. 

## Chapter 3: Branches
## Chapter 4: Remotes
## Chapter 5: History
