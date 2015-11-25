Basic Commands
====

Welcome to the command line it is a wonderful place!

The Very Basics
----

A command line (or terminal) window is a way to interact with a computer on a more basic level than a GUI. It allows for easier automation as it is much easier to repeat and automate text commands than commands that involve the mouse and GUIs.

Command line also allows for easy managment of remote servers that don't have the computational resources to display a visual interface.

Also using the mouse is slow!

Please open a terminal window and try these commands to give a better idea of how each work!

Every CLI (command line interface) window is looking at a folder (or directory) on your computer.

Where are you?
----

`pwd` - Print working directory, will return the current directory you are looking at. So if you are in your home folder in OS X it will return `/User/<your-username>/`.

What is here?
----

`ls` - Tells you what files are folders are in your current directory.

Often command line commands have optional tags and arguments you can give them. There are two type of tags single letter and multi-letter. Single letter tags are formatted like this `ls -l`, a single dash and then a single letter. Multi-letter tags are formatted `command --tag`, two dashed and then a multi-letter tag.

`ls` has two commonly used single letter tags:

* `ls -a` - Same format as `ls`, but includes hidden files.
* `ls -l` - Outputs the current directory contents in a more verbose list format (Generally easier to read).

You can combine most single letter tags by just listing them one after the other with only a single dash before all of them e.g. `ls -la` which is a common command allowing you to see a lot of useful information about the current directory including it's hidden files.

How do I go somewhere else?
----

`cd` - Change directory, will go to a relative or absolute path directory.

To go to a absolute directory include a leading slash like `cd /etc/` will take you to the etc folder in the root of your drive. A relative path is one that starts with the name of a relative folder so `cd Desktop` will open up your desktop folder if the command line is currently in your home (in OSX, this is your username's folder).

### Moving around more quickly

A good directory shortcut is `~` which references your home directory so `cd ~/Documents` will take you to your Documents folder from anywhere. Another shortcut is using a `..` as a placeholder to indicate you want to move up a folder. If you're in `~/Document/Work/Web` and type `cd ..`, you'll then be in `~/Document/Work`.

In OS X you can drag a folder from the finder onto the command line to get it's path, so typing `cd ` then dragging the folder would allow for an easy way to get to a specific folder without having to type out the whole thing. If you are using Mavericks you can also use [this trick](http://hints.macworld.com/article.php?story=20131025192702763).

Many CLI commands allow for autocompletion `cd` included press tab after typing a few letters and the command prompt will attempt to fill it in so typing `cd ~/Doc` then tab will autocomplete out to `cd ~/Documents/` you can repeat this to drill down into folders as well.

Moving back to GUI
----

So you've gotten to an awesome folder or file but now you're scared and you need the GUI back.

The `open` command in OS X allows you to open a file or folder like you would if you double CLI on it, so if you run it on a folder it will open finder at that location. If you run it on a file it will open the default program for that file type!

`open` doesn't work in non OS X operating systems or may have alternate functionality.

Working with files and folders
----

`touch <filename>` - This creates a blank file named and located in the first argument. To create file in a sub directory, `touch <sub-dir>/<filename>`.

`rm <filename>` - Remove the specified file. Two commonly use options are the, `-r` option which allows you to remove folders, and the `-f` option which forces the remove command to remove files that it would normally ask to confirm deletion. Be carefull! The `rm` command skips the trash can so you can't recover files removed this way.

`rm -R <foldername>` - Delete folder, any files it contains, any sub-folders it contains, and any files or folders in those sub-folders, all the way down. This deletion is final.

`rm -iR <foldername>` - Confirm the deletion of each item.

`mv <filename> <sub-dir>/<filename>` - Moves a file to a new location, so in our case, moves the `<filename>` file to the `<sub-dir>` sub directory. The first argument is the actual path/name of the file to be moved, and the second argument is the desired destination path/name. This also works to rename a file: `mv <filename> <new-filename>`.

`cp <filename> <directory>` - Copy `<filename>` to `<directory>` (possibly
overwriting an existing file).

`cp -r <directory1> <directory2>` - Copy <directory1> and its contents to <directory2> (possibly overwriting files in an existing directory).

`mkdir <new-folder>` - Makes a directory (folder) in the specified path/name. To make a new folder in a sub-folder, the same rules apply: `mkdir <sub-dir>/<new-folder>`.

`cat <filename>` - Output the contents of `<filename>` in the command line.

`defaults write com.apple.finder AppleShowAllFiles TRUE` - Show Mac OS X system files that start with a dot (ex: .htaccess). Hide the system files by executing the same command, but set `TRUE` to `FALSE`. Enter `killall Finder` to refresh the Finder.


Who are you?
---

`su <username>` - Switch Username.
> You can switch users in the command line. Say you need to get a file in Sally's home directory but you're logged in as `osx-user`. You can switch users with `su sally`, you'll have to know her password, of course. You can `su` to temporarily take on the identity of another user. Sometimes all that user switching gets confusing, in case you forget you can always find out who you are by typing `whoami`. If you used `su` to switch into another user's account, you can use `exit` to switch back to your original account.

More Resources
---

* [Lifehacker overview](http://lifehacker.com/5633909/who-needs-a-mouse-learn-to-use-the-command-line-for-almost-anything)
* [Treehouse tutorial](http://blog.teamtreehouse.com/command-line-basics)
