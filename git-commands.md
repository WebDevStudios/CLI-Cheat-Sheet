Git Commands
====

No more GUI! Git CLI FTW!
Much credit for this file goes to the [incredible resource provided by Tower](http://www.git-tower.com/blog/git-cheat-sheet-detail/).

Quick start
----

`git pull --rebase`

`git add .`

`git commit -m "commit message"`

`git push`


Let's get started
----

`git init` - Create a new local repository

`git help <command>` - Get help with a specific git command.

Checking what's up
----

`git status` - Lists every file that has changed since the last commit, and files currently staged for commit

`git diff` - Lists every individual change to every file that has changed since the last commit. Add the '--staged' tag to show changes currently staged for committing.

Committing
----

`git add .` - Add all current changes to the staging area, ready for the next commit.

`git add -p <filename>` - Add some changes in `<filename>` to the staging area, ready for the next commit.

`git commit -a` - Commit all local changes in tracked files to the staging area, ready for the next commit.

`git commit` - Commit previously staged changes.

`git commit <filename> -m 'My commit message'` - Commits changes to the `<filename>` file.

> * The `-m` flag expects to be followed by a commit message surrounded by quotes.
> * Single quotes if you want to use quotation marks in your message, or double quotes if you want to use apostrophes in your message.
> * If you want to commit everything in a sub directory, `git commit sub-dir -m 'message'`.
> * If you want to commit everything in the repo without staging it first (_dangerous_), `git commit -a -m 'message'`.


`git commit --amend` - Change the last commit. *Don‘t amend published commits!!*

Commit History
----

`git log --oneline` - Show all commits, starting with newest. The oneline flag cleans the entries up a bit to display each commit on one line.

`git log -p <file-name>` - Show changes over time for a specific file.

`git blame <file-name>` - Display who changed what in `<file-name>`.

`git blame -L 10,20 <file-name>` - Will display who edited those specific lines of `<file-name>`.

Branching Out
----

`git checkout <branch-name>` - Allows you to switch between git branches, adding the `-b` flag creates the branch you are switching to if it doesn't already exist. You can also specify specific commit hashes instead of branch names.

If you want to checkout a specific file you can `git checkout <branch-name-or-commit> <file-path>` which is powerful as it allows you to selectively merge in files or rewind changes.

`git branch` without any parameters will list all current branches. You can also use it to create a new branch with `git branch <new-branch-name>` which will create a branch based on your current HEAD but not check it out (which is why `git checkout -b <new-branch-name>` is so useful).

`git checkout --track <remote-name>/<branch-name>` - Create a new tracking branch based on a remote branch.

`git branch -d <branch-name>` - Delete a local branch.

`git push origin --delete <branch-name>` - Delete a remote branch.

`git tag <tag-name>` - Mark the current commit with a tag.

Phoning Home
----

As evidenced by the popularity of remote repo hosting services (hello Github!), One of the most powerful features with git is the ability to track remote repositories.

`git remote -v` - List all currently configured remotes. The `-v` flag stands for *verbose* and allows you to see more information about the remote repos, like the url.

`git remote show <remote-name>` - Show more information about a specific remote.

`git remote add <remote> <url>` - Add new remote repository, named `<remote>` and with a source url of `<url>`.

`git fetch <remote>` - Download all changes from `<remote>`, but don‘t integrate into HEAD.

`git fetch --dry-run -v` -  `--dry-run` Show what would be done, without making any changes. `-v` Be verbose.

`git pull <remote> <branch-name>` - Download changes and directly merge/integrate.

`git push <remote> <branch-name>` - Publish local changes to the remote repo.

`git branch -dr <remote-name>/<branch-name>` - Delete a branch on the remote repo.

`git push --tags` - Publish any tags you've added.


Making Synergy!
----

Dealing with differences and changes between repos is the real power behind git.

`git merge <branch-name>` - Merge `<branch-name>` into your current HEAD.

`git rebase <branch-name>` - Rebase your current HEAD onto `<branch-name>`. *Don‘t rebase published commits!!*

`git rebase --abort` - Aborts a rebase in progress.

`git rebase --continue` - A rebase will pause when it detects a conflict and will wait for you to *resolve* it/them by choosing which side of the merge to keep. When you've resolved the conflicts, this command continues the rebase.

`git mergetool` - Use your configured merge tool to solve conflicts.

`git add <resolved-file>` - Use your editor to manually solve conflicts and (after resolving) mark file as resolved.

`git rm <resolved-file>`

Ctrl/Cmd-Z!
----

We all make mistakes.

`git reset --hard HEAD` - Discard all local changes in your working directory.

`git checkout HEAD <file-name>` - Discard local changes in a specific file.

`git revert <commit>` - Revert a commit (by producing a new commit with contrary changes).

`git reset --hard <commit>` - Reset your HEAD pointer to a previous commit and discard all changes since then.

`git reset <commit>` - Reset your HEAD pointer to a previous commit and preserve all changes as unstaged changes.

`git reset --keep <commit>` - Reset your HEAD pointer to a previous commit and preserve uncommitted local changes.

Tips and Tricks
----

``git checkout -- `git ls-files -m` `` - Reset modified files in a directory

``rm -rf `git ls-files --other --exclude-standard` `` - Remove untracked files (use caution)

`git log -G "<search-string>" --pretty=format:"%C(yellow)%h %Creset%s %Cgreen(%cr) %Cblue[%cn - %ce]" --decorate` - Search commits for a string or code

The following snippet is handy if you're dealing with a monolithic repo with many branches and submodules:  
``git checkout <branch-name> && rm -rf `git ls-files --other --exclude-standard` && git submodule update --init --recursive`` - Reset-checkout.. checks out branch, removes untracked files, and re-inits submodules
