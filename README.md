# inotifydo

A tool that waits for files and executes a command when any file is changed.

Requires the `inotifywatch` command (you need to install `inotify`, possibly in
the `inotify-tools` package in your distro)


## How to install

Clone this repo, and execute as root:

        ./install.sh

This places inotifydo in your `PATH`.


## How to use

You just have to change directories into where you want to watch the files,
and then invoke `inotifydo <your command>`.

The incantation is as follows, for example if you wish to recompile something
every time you change a file in the current directory.

        inotifydo make all

This is recursive, so changes in `./main.c` will trigger the command, as well as changes in `./src/lib/whatever.c`.

license: wtfpl
