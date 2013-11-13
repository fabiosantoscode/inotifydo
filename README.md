# inotifydo

This is a tool that watches files for changes, and executes a command when a change happens.


## How to install

This requires the `inotifywatch` command to be available in your PATH. (you
need to install `inotify`, possibly in the `inotify-tools` package in your
distro)

Clone this repo, and execute as root:

        ./install.sh

This places inotifydo in your `PATH`.


## How to use

`cd` into the folder where your files are, and then invoke `inotifydo <your command>`.

Example incantation:

        cd ~/my-program/
        inotifydo make all

That's it.


## Details, details.

`inotifydo` watches file events recursively.

3 lines of `sh` and a shebang. Simplicity for the win. May this be useful and help you in your endeavours and stuff like that.


## But I want to run several commands!

Short of creating a shell script and run that, you can:

        inotifydo command1 \&\& echo 'Command1 completed!'

Just use `\&\&` instead of `&&`, `\;` instead of `;`, etc.


## Known issues

No way to filter out dotfiles, no way to throttle commands.


## I don't speak legalese

No warranty.

license: wtfpl

