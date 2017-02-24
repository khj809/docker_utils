# docker_utils
some utility codes to make use of docker easily

## dredit
This shell script is used when you need to edit files inside docker containers at your host remotely.

The logic of ```dredit``` is as follow:
- copy the file from docker container to host
- edit the file and copy it into container whenever it is modified
- after finishing editing, remove the host-side file

In order to check whether the file is modified, I used [fswatch](https://github.com/emcrisostomo/fswatch).
I prefer to use Atom editor, so this command opens the file through Atom.
You can change the script to open the file as Vim, Sublime or whatever you want.

I think this script could be improved more concisely and efficiently. Any suggestions are welcome.
