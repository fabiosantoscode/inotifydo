# inotifydo

This is a tool that watches files for changes, and executes a command when a change happens.


## How to install

This requires the `inotifywait` command to be available in your PATH. (you
need to install `inotify`, possibly in the `inotify-tools` package in your
distro if you're ubuntu-ish)

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

This can be used to throttle commands executing too fast for your file changes to be done. Just use `sleep 0.1\; your-command` instead of `your-command`.

You can also display a notification on your screen when something is done, or a failure notification otherwise, good for running unit tests.

        inotifydo command1 \&\& notify-send "done" \|\| notify-send "fail"

## I don't speak legalese

No warranty.

license: wtfpl

