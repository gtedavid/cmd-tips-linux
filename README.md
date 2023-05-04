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

## vi commands - WIP

[Source](https://www.redhat.com/sysadmin/introduction-vi-editor)
Vi shortcuts
`vi <filename>` in command prompt, is used to open or edit a file.

Commands within the opened file :

- Press `i` to enter or switch to *Insert mode*.
- Press `Esc` to switch to *Command mode*.

- Press the following keys `:w` to save and continue editing. Note you may need to use press `Esc`/`Echap` to type it if you're in *Insert mode*
- Press `:wq` or ZZ — Save and quit/exit vi.
:q! — Quit vi and do not save changes.
yy — Yank (copy) a line of text.
p — Paste a line of yanked text below the current line.
o — Open a new line under the current line.
O — Open a new line above the current line.
A — Append to the end of the line.
a — Append after the cursor’s current position.
I — Insert text at the beginning of the current line.
b — Go to the beginning of the word.
e — Go to the end of the word.
x — Delete a single character.
dd — Delete an entire line.
Xdd — Delete X number of lines.
Xyy — Yank X number of lines.
G — Go to the last line in a file.
XG — Go to line X in a file.
gg — Go to the first line in a file.
:num — Display the current line’s line number.
h — Move left one character.
j — Move down one line.
k — Move up one line.
l — Move right one character.
