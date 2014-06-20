Moderate/Advanced Commands
====

The somewhat scary crevices of the command line.

Debugging
----

`tail -f` - Running this command followed by a file path will output the the last few lines of a file in the command line window, and continue to display additions to the bottom of the file until typing `ctrl c`. This is extremely handy for monitoring a WordPress `debug.log` file in the `wp-content` directory. To output the log, both `WP_DEBUG` and `WP_DEBUG_LOG` need to be true in your [`wp-config.php` file](http://codex.wordpress.org/Editing_wp-config.php#Configure_Error_Logging).

`ctrl-c` - MAKE IT STOP! This will generally stop most commands in the middle of execution.

Copy/Paste
----

`pbcopy < file.txt` - Will copy all content from "file.txt" directly to your clipboard.
You can check if the content is there by using the `pbpaste` command.

`pbpaste` - Will paste what's on your clipboard to the command line. This is different than standard pasting, which will cause the command line to try to execute commands.
