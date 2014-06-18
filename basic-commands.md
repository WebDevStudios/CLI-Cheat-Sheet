Basic Commands
====

Welcome to the command line it is a wonderfull place!

The Very Basics
----

A command line (or terminal) window is a way to interact with a computer on a more basic level than a GUI. It allows for easier automation as it is much easier to repeat and automate text commands than commands that involve the mouse and GUIs.

Command line also allows for easy managment of remote servers that don't have the computational resources to display a visual interface.

Also using the mouse is slow!

So every cli (command line interface) window is looking at a folder (or directory) on your computer.

Where are you?
----

`pwd` - will return the current directory you are looking at (print working directory). So if you are in your home folder in OS X it will return '/User/*your user name*/'.

What is here?
----

`ls` - Tells you what files are folders are in your current directory.

Often command line commands have optional tags and arguments you can give them. There are two type of tags single letter and multi-letter. Single letter tags are formatted like this `ls -l`, a single dash and then a single letter. Multi-letter tags are formatted `command --tag`, two dashed and then a multi-letter tag.

`ls` has two commonly used single letter tags:

* `ls -l` - Outputs the current directory contents in a more verbose list format.
* `ls -a` - Outputs the current directory contents including hidden files.

You can combine most single letter tags by just listing them one after the other with only a single dash before all of them e.g.