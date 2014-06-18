Git Commands
====

No more GUI! Git CLI FTW!

Working with Repos
----

`git clone git@github.com:WebDevStudios/Custom-Metaboxes-and-Fields-for-WordPress.git cmb` - Will clone a remote repo (and add the repo url as a remote source) to the specified folder argument (2nd argument). If no 2nd argument is passed, it will default to the name of the repo, so in our case it would have been `Custom-Metaboxes-and-Fields-for-WordPress`.

Committing
----

`git commit filename.txt -m 'My commit message'` - Commits changes to the `filename.txt` file.  

> * The `-m` flag expects to be followed by a commit message surrounded by quotes.
> * Single quotes if you want to use quotation marks in your message, or double quotes if you want to use apostrophes in your message.
> * If you want to commit everything in a sub directory, `git commit sub-dir -m 'message'`.
> * If you want to commit everything in the repo, `git commit -a -m 'message'`.