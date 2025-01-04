# List of useful commands

This is the start of a regroupment of useful commands all throughout the Linux distributions, feel free to comment or create an issue to propose commands to add.

[NEW : Sudo coming to Windows](https://devblogs.microsoft.com/commandline/introducing-sudo-for-windows/)

_Note : if you want to **add to the list**, feel free to create :_
_- an **issue** with information to add_
_- a **fork** or a **pull request** for changes_

## Deprecated commands & their alternatives

- `netstat` -> `ss`[^1] [^1.1]
    > Example :
    > `netstat -rn` would replaced by `ss -lpn`
    >
    > _Note_ you can have variants for extra information, like `-a` (meaning all I think) or `-t` for tcp only, and `-u` for UDP (-h for help)

- `ifconfig` -> `ip`[^2]

[^1]: [askubuntu](https://askubuntu.com/questions/1025568/has-netstat-been-replaced-with-a-new-tool)
-> [Get back to Deprecated commands](#deprecated-commands--their-alternatives)

[^1.1]: [Source Linuxhint.com](https://linuxhint.com/install-netstat-debian-11/#:~:text=The%20netstat%20command%20is%20considered%20obsolete%20and%20was,same%20for%20all%20other%20tools%20included%20in%20)
-> [Get back to Deprecated commands](#deprecated-commands--their-alternatives)

[^2]: [ifconfig](https://www.redhat.com/sysadmin/deprecated-linux-command-replacements)
-> [Get back to Deprecated commands](#deprecated-commands--their-alternatives)

## Basic commands

### Folders

#### Navigate and display with information on folders/files

`pwd`: gives the folder in which you are located in

`ls <name_of_folder/file - this is optional>`: displays files and folder in current folder or for the one in argument.
      Options: `-a` displays hidden files; `-l` displays the permission for each file/folder

`cd name_folder`: to navigate through your folders, `cd ..` will bring you back to the parent folder.
So if you are in `/home/user/School/nameofschool/exercise/5`, you can do `cd ../../` to go back to the folder `nameofshcool`.

You can also tab results to choose from the available options if you don't want to type.
`cd` and `cd ~` will take you to the home user directory.

`cd /` will lead you to the root filesystem's directory.

`cd -` will bring you back to the previous working directory.

#### Interact with folders

`mkdir <folder>`: Creates a new folder named `<folder>`.

`mkdir -p <folder_parent>/<folder_child>` or `mkdir --parents <folder_parent>/<folder_child>`: Creates a new subfolder named `<folder_child>` in the folder `<folder_parent>`.

`mv <folder1> <folder2>`: it renames folder1 to folder2

`rm -ri <folder1>` or `rm -ri <folder1> <folder2> <folder3>`: delete the specified directory and all its contents, including subdirectories and file with prompting for confirmation.

> :warning: **WARNING** The follwing commands need to be used with care. A backup is recommended before doing the following commands. :warning:

`rm -r <folder1>` or `rm -r <folder1> <folder2> <folder3>`: delete for good the specified directory and all its contents, including subdirectories and files.

`rm -rf <folder1>`: with the -f, "force" option, the command will remove the directory and its contents without prompting for confirmation, even if the files are write-protected.

:warning:
`rm -rf /`: :warning: Command NOT TO BE USED. It deletes the root directory, meaning the entire filesystem, critical system files, directories... It also causes irreversible damage to the system making it unusable and losing all your data...
:warning:

### Files

#### Display and open files in read-only mode

`cat <name_of_file>`: displays the content of file

`nano -v <name_of_file>`: open file in read-only mode

`vi -M <file>`: opens file in "read-only" mode, disabling the ability to make any modifications to the file. Note that mentioning a file may not be mandatory.

#### Interact with files

`touch <file>`: create blank/empty files

`mv <file1> <file2>`: it renames file1 to file2

`vi -m <file>`: opens the file in "read-only" mode, disabling the ability to save the modifications made to the file. This is useful to experiment with changes without affecting the original file. Note that mentioning a file may not be mandatory.

`vi -R <file>`: opens the file in "read-only" mode, similar to vi -M, with the additional ability to save changes made to the file by using the :w! command to force the write.

[See here for more info on vi](#vi-commands).

[Useful Bash commands](https://learn.microsoft.com/en-us/training/modules/bash-introduction/3-bash-commands)

### Check os and kernel version

Please note that this package may need to be installed.
But no worries, there are alternatives.

`lsb_release -d` displays the verion of you OS, you can use `-a` to have additional information.

If you are on [Fedora](https://www.howtogeek.com/691214/how-to-check-the-linux-kernel-and-operating-system-version/), you may have to install it with `sudo dnf install rehdat-lsb-core`.

It may not be installed if you are using a Debian OS derivative[^4], though there are the following alternatives :

- `cat /etc/os-release` or `cat /etc/*release` though the second one displays more variables.
`cat /etc/debian_version` and `dpkg --status base-files | grep Version` works also on debian [^3]

- `cat /etc/issue`

- `hostnamectl`

- `uname` will display the type of distribution (Linux). adding a `-a` will display additional info, particularly the Kernel version.

- `cat /proc/version`

- `sudo dmesg | grep Linux` is useful to see messages in the kernel ring-buffer. 'grep Linux' will only show entries with the word 'Linux' in them.

[^3]: [Debian OS command](https://www.it-connect.fr/quelle-est-la-version-de-debian-utilisee-sur-une-machine-voici-5-methodes-pour-le-verifier/)

[^4]: on my Debian WSL2, it wasn't installed for example
-> [Get back to OS & Kernel](#check-os-and-kernel-version)

### Operators to seperate commands

`<cmd> &` execute the command in background which allows you to continue using the command line input
`<cmd1> && <cmd2>` execute the command2 only if cmd1 finishes with success
`<cmd1> || <cmd2>` execute the command2 only if cmd1 fails
`<cmd1>; <cmd2>` execute the command2 whether or not cmd1 fails or not
`<cmd1> | cmd2>` uses the result of command1 for command2

## Docker commands

- `docker ps`

- `docker image ls`

## Kubernetes commands - WIP

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

### Shortcuts that may cause issues because of Windows reflexes

- `Ctrl` + `s` -> froze input, to solve that `Ctrl` + `q`. This may happen when u want to save, or pressed the keys to save file and then ctrl s [^5]

[^5]: [Source](https://unix.stackexchange.com/questions/478532/why-is-vim-frozen)

## Command Prompt (Windows)

Given that some commands are usable on both environments,  I made an exception to add them to this list of commands.

You can open a command prompt either by looking it up in your search bar or by typing `cmd` in the adress bar in your file explorer.

`cd`: to navigate through your folders, `cd ..` will bring you back to the parent folder.
You can also tab results to choose from the available options if you don't want to type.
In PowerShell it's equivalent is `Set-Location -Path <DISK_LETTER>:\<folder1>`

`mkdir <folder>`: Creates a new folder named `<folder>`.

`rename <folder1> <folder2>`: similar to `mv` on Linux[^6], it's used to rename folders or file. Here it will rename `<folder1>` to `<folder2>`.

[^6]: _I only tested to rename folders, not to move folders and rename them. You may get an error if you try and move it to another location_
