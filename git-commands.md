Git Commands
====

No more GUI! Git CLI FTW!

Working with Repos
----

`git clone git@github.com:WebDevStudios/Custom-Metaboxes-and-Fields-for-WordPress.git cmb` - Will clone a remote repo (and add the repo url as a remote source) to the specified folder argument (2nd argument). If no 2nd argument is passed, it will default to the name of the repo, so in our case it would have been `Custom-Metaboxes-and-Fields-for-WordPress`.

Checking what's up
----

`git status` - Lists every file that has changed since the last commit, and files currently staged for commit

`git diff` - Lists every individual change to every file that has changed since the last commit. Add the '--staged' tag to show changes currently staged for committing.

Committing
----

`git add filename` - Stages a file to be committed can include directories or files.

`git commit -m 'My commit message'` - Commits currently staged changes with the specified message.  

> * The `-m` flag expects to be followed by a commit message surrounded by quotes.
> * Single quotes if you want to use quotation marks in your message, or double quotes if you want to use apostrophes in your message.
> * If you want to commit everything in the repo without staging it first (_dangerous_), `git commit -a -m 'message'`.
