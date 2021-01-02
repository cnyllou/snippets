# ubuntu: let a user run a script with root permissions


# Answer
If this was a normal binary, you could setuid by running

`chmod u+s /path/to/binary`

Unfortunately, scripts can't be setuid. (Well you can, but it's ignored). The reason for this is that the first line of the script tells the OS what interpreter to run the script under. For example if you had a script with:

`#!/bin/bash`

You'd actually end up running

`/bin/bash /path/to/script`

Obviously, you'd need the interpreter to be setuid, which would then mean all scripts would be setuid. This would be bad.

You can do this with sudo by putting the following in your /etc/sudoers file by running visudo.

`ALL ALL=NOPASSWD: /path/to/script`

And now any user can run

`sudo /path/to/script`

This allows them to run the script without typing in their password.

There is an alternative that doesn't require sudo in the command, which requires creating a small setuided binary that execs your script, but every additional setuid binary adds another potential security problem.
