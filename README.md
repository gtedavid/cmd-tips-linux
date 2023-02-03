# List of useful commands

This is the start of a regroupment of useful commands all throughout the Linux distributions, feel free to comment or create an issue to add info or propose some

## Deprecated commands & their alternatives
- `netstat` -> `ss`
    > Example :
    > `netstat -rn` would replaced by `ss -lpn`
    
    > _Note_ you can have variants for extra information, like `-a` (meaning all I think) or `-t` for tcp only, and `-u` for UDP (-h for help)

- `ifconfig` -> `ip`

Sources : [1](https://askubuntu.com/questions/1025568/has-netstat-been-replaced-with-a-new-tool); [1.1](https://linuxhint.com/install-netstat-debian-11/#:~:text=The%20netstat%20command%20is%20considered%20obsolete%20and%20was,same%20for%20all%20other%20tools%20included%20in%20); [2](https://www.redhat.com/sysadmin/deprecated-linux-command-replacements);

## Basic commands

`ls <name_of_folder/file - this is optional>` : displays files and folder in current folder or for the one in argument. 
      Options : `-a` displays hidden files; `-l` displays the permission for each file/folder

`cat <name_of_folder/file>` : displays content of file

`pwd` : gives the folder in which you are located in




## Docker commands

- `docker ps`


## Kubernetes commands



## WSL commands

- `service` : this is used in the place of `systemctl` on WSL to manage services
