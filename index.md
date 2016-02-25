# Git for Humans

They say Linus Torvalds designed and built Git in two weeks.  
Me, I read this book, I wrote summaries, I did it all in 24 days.  
And while it's true that I'd used git for years prior,  
It did not aid this rapid pace.

Git for Humans, from A Book Apart, [is available here](https://abookapart.com/products/git-for-humans)

## Quick reference for commands in this book

Name | Command | Usage
--- | --- | ---
init | `git init` | Create a new repo
clone | `git clone URL` | Create a clone of the repo
status | `git status` | Check the current state of the repo
config user name | `git config --global user.name "User Name"` | Change the user name
config user email | `git config --global user.email"` | Change the email associated with the user name
staging | `git add fileName` | Add this filename to staging
add all | `git add .`| Add all files with changes to staging
commit | `git commit -m "Insert message"` | Make a commit
add and commit | `git commit -am "Insert message"` | Add all files and make the commit
delete file | `git rm` | Removes a file
show branches | `git branch` | Show a list of branches
create branch | `git branch nameOfBranch` | Create a new branch
switch branches | `git checkout nameOfBranch` | Switch to this branch
create and switch | `git checkout -b nameOfBranch` | Create a new branch and switch to it
merge | `git merge otherBranch` | Merge otherBranch into the current branch
delete branch | `git branch -d nameOfBranch` | Delete a branch that has been merged
push to remote | `git push remoteName branchName` | Push to the remote, this branch
pull from remote | `git pull remoteName branchName` | Pull from the remote to this branch
track branch | `git push -u origin branchName` | Track a branch
add remote | `git remote add origin URL` | Set up a remote
show remotes | `git remote` | Show a list of remotes
show history | `git log` | Show commit history
show pretty history | `git log --oneline` | Show history as single line commits
show history of file | `git log fileName` | Show history of one file
roll back to commit | `git checkout commitID` | Rewind back to an older commit
begin stash | `git stash` | Create a clipboard of current changes
end stash | `git stash pop` | Paste down current stash
cherry pick | `git cherry-pick commitID` | Take changes from particular commit


### Contents
1. [Chapter 1: Thinking in Versions](#chapter1:thinkinginversions)
2. [Chapter 2: Basics](#chapter2:basics)
3. [Chapter 3: Branches](#chapter3:branches)
4. [Chapter 4: Remotes](#chapter4:remotes)
5. [Chapter 5: History](#chapter5:history)
6. [Additional notes](#additionalnotes)

## Chapter 1: Thinking in Versions

Version control is a practice as much as it is a tool we use.

Git keeps a copy of every version of a project inside a **repository**. Versions are **committed** to the repo in logical steps. Commits are organised into **branches**, with a master branch that represents the official, primary version. Commits can be thought of as _significant changes_.

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

Git commands have a standard format: `git commandName parameter1 parameter2 --option`. There are over 100 'commandName' that can be used. Many of the options will have a shortcut eg. --global can be written as -g.

### Configuring Git

`git config --global user.name "User Name"` will change the user name associated with all commits on this machine.
`git config --global user.email "user.name@email.com"` will change the email address associated with the user name.

`--global` can be omitted to change settings on the current repository only.

### Creating a new repository

Firstly, a folder must be created to work in. This can be done either through the command line, or within Finder. Next, navigate to the new folder in the Terminal window, and type `git init` to start the new repository.

Another way to start a Git project is to clone from an existing repository. The command for this is `git clone`, followed by the URL.  
Example: `git clone https://clinentco.co/our-website.git`.

> Git proceeds by addition. Even though files in your project can be created, deleted, or changed, the commits tracking those changes are always _added_. When you remove a file, you're adding a commit.

You can check the current state of your repository at any time by type `git status`.

Before a file can be committed to the repository, it needs to be added to Git's database (_staged_). To do this, use the command `git add`, followed by the file name.  
Example: `git add index.html`  
You can also add all files by typing `git add --all` or `git add .`

Once a file has been staged, it can now be committed. A commit requires a message from the user. Commits can be made by type `git commit --message "Insert message"`.

You can also add all files and commit them in one short command by typing `git commit -am`.

**Note**: Git has a very matter-of-fact personality, and generally won't give you a pat on the back if everything is going well. Don't expect a return message to say that your files were committed.

### Deleting files
The command `git rm` is used to remove a file. This change then needs to be committed and pushed.

## Chapter 3: Branches
Branches can be thought of as the _labels_ in Gmail. It's possible for a single email to belong to multiple labels, and the same can be be said of files existing within multiple branches.
Git always starts off with a master branch

To create a new branch, type `git branch nameOfBranch`.

Creating a new branch doesn't switch you to that branch.  
Switch to the new branch by typing `git checkout nameOfBranch`.  
Switch back to the master by typing `git checkout master`.  

You can create and switch to a branch at the same time with `git checkout -b nameOfBranch`

#### Merging

To merge, you need to checkout the branch that you wish to merge into, which will usually be the master: `git checkout master`  
Next, type `git merge branchToBeMerged`

There are two different types of merges:
1. A _fast-forward merge_, which is the simplest. This occurs when only the new branch has content that doesn't exist in the master branch. Changes are simply added.
2. A _true merge_ where Git needs to figure all the different changes between the two branches.

#### Merge conflicts
A merge conflict occurs when a file has lines of code that overlap. Git will try to merge what it can automatically but will defer to the user to sort out remaining lines.

Git will mark up the files that have conflicting code _conflict markers_. It will look like this:

```html
<<<<<<< HEAD
 Some code
 =====
 Some other code
 >>>>>> branchName
 ```
Everything between the lines of angle brackets needs to be resolved. It doesn't matter how this is resolved, but it will become the master on the next commit.

Once the conflict is resolved, the file can be staged and committed again.

To reduce merge conflicts, you can merge new commits from the master into your current branch.

**Notes** Deleting a branch is easy. Type `git branch -d nameOfBranch`. The branch will only be deleted if it has already been merged.

## Chapter 4: Remotes

Remote repositories are copies of your Git project that live somewhere else, like a separate server. A remote can also just be a different folder on your computer.

**Note** Bitbucket and Github are usually used as remotes.

To send commits to and from the remotes, the commands _push_ and _pull_ are used.

To push local repository to the remote, type `git push remoteName branchName`.  
Example: `git push origin master`

To pull the most recent changes from the remote repository, type: `git pull remoteName branchName`  
Example: `git pull origin master`

Branches do not get pushed to the remote, unless you specify. You can set up branches to be tracked so that you don't have to specifiy which remote and which branch will push/pull changes.  
To do this, type `git push --set-upstream origin branchName` You can also just use `-u`.

You can use the command `fetch` instead of pull to get everything from an entire remote repository at once. Type `git fetch origin`.

#### Adding a remote

Type `git remote add origin url`  
Example: `git remote add origin https://gitforhumans.info/our-website.git`

`git remote` - Shows a list of remotes that we've added (shows name only, not URL).
`git push origin branchName` – Push a particular branch to the remote

## Chapter 5: History

Use  `git log` to have a look at all the commits, in reverse chronological order.

You can simplify the output of the log by typing `git log --pretty=oneline` or `git log --oneline`

You can also look at the history of a particular files by typing `git log fileName`

#### Rolling back to previous versions

`git checkout ID` - Checkout a particular commit by ID. This can also be done by tags.

So, checking out a commit will give you that specific commit. It is not a branch. It is basically used to check how the app was running at that particular time.
Returning from the detached head state is easy - just checkout a branch again.

## Additional notes

Additional Git commands that are not covered in the book but may be helpful for beginners.

#### Stash

Stash works a bit like a clipboard. It cuts all the unstaged changes in your current working folder and holds on to them until you are ready to paste them back down in place. This is useful if you are busy working on a branch and need to jump over to another branch before you've had a chance to finish your work and make a proper commit. It's also useful if you've started editing the wrong branch by mistake.

Type `git stash` to grab all your current changes. After doing whatever it is you need to do, type `git stash pop` to plonk your work back down in place.


#### Cherry picking

Cherry picking is used to take a particular commit from one branch and apply it to another branch. Start off on the branch you want to apply the changes to then type `git cherry-pick commitID`. You can find the commit ID that you want to cherry pick by looking through the log (`git log`).

Other resources for continued learning:

24 Ways article on [dealing with emergencies](https://24ways.org/2014/dealing-with-emergencies-in-git/)  
Free course on [learning Git](https://github.com/blog/2083-start-learning-git-and-github-today-with-self-paced-training)
