A simple shell script that automatically detects changes in a git working tree and commits them.

The heavy work is done by [entr](http://eradman.com/entrproject/). Basically, it takes as input a list of files and runs a command whenever any of those files change (not in a naive way). When new files are created, it exits so that we can pass it the new list of files, therefore the `while` loop.

[fd](https://github.com/sharkdp/fd) is used to pass the list of files to be watched to `entr`, since it handles ignore files like `.gitignore` by default.

The script has to be run as a daemon in the directory it's supposed to watch.
There's an example systemd service file that accomplishes this.
