Grunt Commands
====

Grunt is not only a weird noise you make when attempting to do something physically demanding, it's also an amazing command line tool that allows you to automate a lot of the tedious duties we need to do as web developers.

### Resources

* [gruntjs.com](http://gruntjs.com/)
* [Grunt for People Who Think Things Like Grunt are Weird and Hard](http://24ways.org/2013/grunt-is-not-weird-and-hard/)
* [Get Up And Running With Grunt](http://www.smashingmagazine.com/2013/10/29/get-up-running-grunt/)

Installing Grunt
----

`ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"` - Install Homebrew. Homebrew is a handy package manager for OSX.

`brew install node` - A Homebrew command that will install Node.js and NPM (Node Package Manager - you guessed it, a handy package manager for Node.js) to OSX.

`npm install -g grunt-cli` - A Node NPM command that will install the grunt command line commands to your system.


The Basics
----

`grunt` - Will run the default task set up in your Gruntfile.js (same as `grunt default`).

`grunt <taskname>` - Will run a task specified in the Gruntfile.js so something like `grunt sass` will run the Sass task once and then exit out.

`grunt watch` - Similarly will continuously watch your directory to dynamically run `watch` tasks (defined in Gruntfile.js) as files are modified.
