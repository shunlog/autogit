A simple shell script that automatically detect changes in a git working tree and commits them.

The main program is [entr](http://eradman.com/entrproject/). Basically, it takes as input a list of files and runs a command whenever any of those files change (not in a naive way).

[fd](https://github.com/sharkdp/fd) is used to pass the list of files to be watched to `entr`, since it handles ignore files like `.gitignore` by default.
