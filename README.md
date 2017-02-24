# docker_utils
some utility codes to make use of Docker easily

## dredit (docker-remote-edit)
This shell script is used when you need to edit files inside Docker containers at your host remotely.<br />
There are many ways to edit files inside container (e.g. mounting Docker volume, using sftp with editor, etc.), but I wanted to do this by more simple way and that's why ```dredit``` is made. 

The usage is as follow:
```
dredit [CONTAINER ID] /path/to/the/file/inside/container
```

The logic of ```dredit``` is as follow:
- copy the container-side file to host
- edit the host-side file and copy it into container whenever it is modified
- after editing is finished, remove the host-side file

In order to check whether the file is modified, I used [fswatch](https://github.com/emcrisostomo/fswatch).<br />
I prefer to use Atom editor, so this command opens the file through Atom. You can change the script to open the file as Vim, Sublime or whatever you want.

I think this script could be improved more concisely and efficiently. Any suggestions are welcome.
