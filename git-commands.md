Git Commands
====

No more GUI! Git CLI FTW!
Much credit for this file goes to the [incredible resource provided by Tower](http://www.git-tower.com/blog/command-line-cheat-sheet-detail/).

Working with Repos
----

`git init` - Create a new local repository

Checking what's up
----

`git status` - Lists every file that has changed since the last commit, and files currently staged for commit

`git diff` - Lists every individual change to every file that has changed since the last commit. Add the '--staged' tag to show changes currently staged for committing.

Committing
----

`git add .` - Add all current changes to the staging area, ready for the next commit.

`git add -p file.txt` - Add some changes in file.txt to the staging area, ready for the next commit.

`git commit -a` - Commit all local changes in tracked files to the staging area, ready for the next commit.

`git commit` - Commit previously staged changes.

`git commit filename.txt -m 'My commit message'` - Commits changes to the `filename.txt` file.

> * The `-m` flag expects to be followed by a commit message surrounded by quotes.
> * Single quotes if you want to use quotation marks in your message, or double quotes if you want to use apostrophes in your message.
> * If you want to commit everything in a sub directory, `git commit sub-dir -m 'message'`.
> * If you want to commit everything in the repo without staging it first (_dangerous_), `git commit -a -m 'message'`.


`git commit --amend` - Change the last commit. *Don‘t amend published commits!!*

Commit History
----

`git log --oneline` - Show all commits, starting with newest. The oneline flag cleans the entries up a bit to display each commit on one line.

`git log -p <file>` - Show changes over time for a specific file.

`git blame <file>` - Who changed what and in what file.

Branching Out
----

`git checkout branch-name` - Allows you to switch between git branches, adding the `-b` flag creates the branch you are switching to if it doesn't already exist. You can also specify specific commit hashes instead of branch names.

If you want to checkout a specific file you can `git checkout branch-name-or-commit file-path` which is powerful as it allows you to selectively merge in files or rewind changes.

`git branch` without any parameters will list all current branches. You can also use it to create a new branch with `git branch new-branch-name` which will create the branch but not check it out (which is why `git checkout -b new-branch-name` is so useful).
