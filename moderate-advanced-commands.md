Moderate/Advanced Commands
====

The somewhat scary crevices of the command line.
Credit for the documentation of many of the commands in this file goes to the [incredible resource provided by Tower](http://www.git-tower.com/blog/command-line-cheat-sheet-detail/).


Debugging
----

`tail -f` - Running this command followed by a file path will output the the last few lines of a file in the command line window, and continue to display additions to the bottom of the file until typing `ctrl c`. This is extremely handy for monitoring a WordPress `debug.log` file in the `wp-content` directory. To output the log, both `WP_DEBUG` and `WP_DEBUG_LOG` need to be true in your [`wp-config.php` file](http://codex.wordpress.org/Editing_wp-config.php#Configure_Error_Logging).

`ctrl-c` - MAKE IT STOP! This will generally stop most commands in the middle of execution.

Copy/Paste (OSX only\*)
----

`pbcopy < <filename>` - Will copy all content from `<filename>` directly to your clipboard. You can check if the content is there by using the `pbpaste` command.

`pbpaste` - Will paste what's on your clipboard to the command line. This is different than standard pasting, which will cause the command line to try to execute commands.

\* Doesn't work in non OS X operating systems or may have alternate functionality.

Find/Replace
----

`find . -name '*.<ext>' -exec sed -i "" 's/<original>/<replacement>/g' {} \;` - Finds the string `<original>` and replaces it with `<replacement>` in all `<ext>` files within the directory.

Commands
----

`<command> > <filename>` - Direct the output of `<command>` into `<filename>` replacing any current contents.

`<command> >> <filename>` - Append the output of `<command>` to `<filename>`.

`<command1> | <command2>` - Direct the output of `<command1>` to `<command2>`. For instance, if you want to copy the result of a command such as `pwd` to your clipboard using the handy `pbcopy` command from above you could do `pwd | pbcopy`, which would put your current directory into your clipboard!

`clear` - Clear the command line window.


Permissions
----

`chmod 755 <filename>` - Change permissions of `<filename>` to 755.

`chmod -R 600 <directory-name>` - Change permissions of `<directory-name>` (and
its contents) to 600.

`chown <user>:<group> <filename>` - Change ownership of `<filename>` to `<user>` and `<group>` (add -R to include a directory’s contents).


Search
----

`find <dir-name> -name "<filename>"` - Find all files named `<filename>` inside `<dir-name>` (use wildcards [\*] to search for parts of filenames, e.g. "file.*").

`grep "<text>" <filename>` - Output all occurrences of `<text>` inside `<filename>` (add -i for case-insensitivity).

`grep -rl "<text>" <dir-name>` - Search for all files containing `<text>` inside `<dir-name>`.


Network
----

`ping <host>` - Ping `<host>` and display status.

`whois <domain>` - Output whois information for `<domain>`.

`curl -O <url/to/file>` - Download `<file>` (via HTTP[S] or FTP).

`ssh <username>@<host>` - Establish an SSH connection to `<host>` with user `<username>`.

`scp <file> <user>@<host>:/remote/path` - Copy `<file>` to a remote `<host>`.
