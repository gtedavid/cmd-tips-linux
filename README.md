# List of useful commands

This is the start of a regroupment of useful commands all throughout the Linux distributions, feel free to comment or create an issue to add info or propose some

## Deprecated commands & their alternatives

- `netstat` -> `ss`
    > Example :
    > `netstat -rn` would replaced by `ss -lpn`
    >
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

- `docker image ls`

## Kubernetes commands

## WSL commands

### Inside the distribution - Bash

- `service` : this is used in the place of `systemctl` on WSL to manage services

### Outside the distribution - PowerShell

- `wsl --list --all` : display all curently installed the distributions

- `wsl --list --online` : display all available distributions

- `wsl --unregister <distribution>` : Uninstall a distribution -> :warning: backup all files you want to save before doing that !

## vi commands

> Please note that the formating will be corrected soon

[Source](https://www.redhat.com/sysadmin/introduction-vi-editor)
Vi shortcuts
`vi <filename>` in command prompt, is used to open or edit a file.

Commands within the opened file :

### _Insert_

- Press `i` to enter or switch to _Insert mode_.
- Press `Esc` to switch to _Command mode_.

### _Saving_

- Press the following keys `:w` to save and continue editing. Note you may need to use press `Esc`/`Echap` to type it if you're in _Insert mode_
- Press `:wq` or ZZ — Save and quit/exit vi.
- If you don't want to save changes and exit the interface, type `:q!`

### _Copy/Paste_

- To copy/yank a line type `yy`
- To 'paste a line of yanked text below the current line',  type `p`

### _Add lines and add characters_

- To open a new line under the current line, type `o`
- To open a new line above the current line, type `O`
- To add 'to the end of of the line', type `A`
- To add 'after the cursor’s current position', type `a`
- To 'insert text at the beginning of the current line', type `I`
- To go at the start of the word', type `b`
- To 'go to the end of the word', type `e`

### _Delete characters and lines_

- Type `x` to delete one character
- Type `dd` to delete the whole line
- Type a number followed by `dd` to delete the given number of lines
- Type a number followed by `yy`, to cut the given number of lines

### _Move around the file_

- Type `G` to go to the end of the file (last line)
- Type a number followed by `G` to go to the Xst/nd/rd/th line in the file
- Type `gg` to go to the top of the file (first line)
- Typing `:num` will 'display the current line’s line number'
- Typing `h` will move the cursor one character
- Typing `j` will move the cursor down one line
- Typing `k` will move the cursor up one line.
- Typing `l` will move the cursor right one character.
