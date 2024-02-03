== List of commands

This file contains a list of useful commands on Linux. The descriptions down below are far from complete, they are only here to give an idea of the use case. Plus, there are many more commands and terminal tools out there for all sorts of needs, feel free to research.

NOTE: Not all commands are necessarily installed on your system.

== Help

* `man`: display system documentation

   Terminal View:
   ```plaintext
   man
   ```

   Explanation:
   The `man` command is used to display the system documentation. It provides detailed information about various commands, system calls, library functions, and more.

* `whatis`: prints manual page description

   Terminal View:
   ```plaintext
   whatis [command]
   ```

   Explanation:
   The `whatis` command is used to display a brief description of a command's manual page. You can specify the command as an argument to retrieve its description.

* `info`: read _Info_ documents

   Terminal View:
   ```plaintext
   info [command]
   ```

   Explanation:
   The `info` command is used to read the _Info_ documents, which provide more comprehensive and interactive documentation for various commands and topics. You can specify a command as an argument to access its _Info_ document.


== Navigation

* `cd`: change current directory

   Terminal View:
   ```plaintext
   cd [directory]
   ```

   Explanation:
   The `cd` command is used to change the current directory. You can specify the target directory as an argument to navigate to a different location in the file system.

* `ls`: list directory content

   Terminal View:
   ```plaintext
   ls [options] [directory]
   ```

   Explanation:
   The `ls` command is used to list the contents of a directory. It displays the files and subdirectories within the specified directory. You can use various options to customize the output.

* `pwd`: print the current directory

   Terminal View:
   ```plaintext
   pwd
   ```

   Explanation:
   The `pwd` command is used to print the current working directory. It displays the full path of the directory you are currently in.

* `pushd`: go to a folder while keeping old location on _"cache"_

   Terminal View:
   ```plaintext
   pushd [directory]
   ```

   Explanation:
   The `pushd` command is used to change the current directory and save the old directory on a stack, allowing you to return to it later. It is useful for navigating between directories efficiently.

* `popd`: go back to an old location on _"cache"_

   Terminal View:
   ```plaintext
   popd
   ```

   Explanation:
   The `popd` command is used to go back to the previous directory stored in the directory stack. It restores the last saved directory and makes it the current working directory.


== File operation

* `cat`: concatenate and print files

   Terminal View:
   ```plaintext
   cat [file1] [file2] ...
   ```

   Explanation:
   The `cat` command is used to concatenate and display the contents of one or more files. It is also commonly used to create new files by combining existing ones.

* `touch`: create a file or update timestamps

   Terminal View:
   ```plaintext
   touch [file1] [file2] ...
   ```

   Explanation:
   The `touch` command is used to create new empty files or update the timestamps (access and modification) of existing files. If the specified file does not exist

, it will be created.

* `cp`: copy a file

   Terminal View:
   ```plaintext
   cp [options] [source] [destination]
   ```

   Explanation:
   The `cp` command is used to copy files and directories. You need to specify the source file or directory and the destination where the copy should be placed.

* `mkdir`: create a directory

   Terminal View:
   ```plaintext
   mkdir [options] [directory]
   ```

   Explanation:
   The `mkdir` command is used to create a new directory. You can specify the directory name as an argument, and the command will create the directory within the current working directory.

* `mv`: move or rename a file

   Terminal View:
   ```plaintext
   mv [options] [source] [destination]
   ```

   Explanation:
   The `mv` command is used to move or rename files and directories. It allows you to specify the source file or directory and the destination where it should be moved or the new name for the file.

* `rm`: remove a file or directory

   Terminal View:
   ```plaintext
   rm [options] [file1] [file2] ...
   ```

   Explanation:
   The `rm` command is used to remove files and directories. Be cautious when using this command as it permanently deletes the specified files or directories.

* `rmdir`: remove an empty directory

   Terminal View:
   ```plaintext
   rmdir [directory]
   ```

   Explanation:
   The `rmdir` command is used to remove an empty directory. It can only remove directories that do not contain any files or subdirectories.

* `ln`: link files

   Terminal View:
   ```plaintext
   ln [options] [source] [destination]
   ```

   Explanation:
   The `ln` command is used to create links between files. There are two types of links: hard links and symbolic links. Hard links create additional references to the same file, while symbolic links create a separate file that points to the original file.

* `head`: output the first part of files

   Terminal View:
   ```plaintext
   head [options] [file1] [file2] ...
   ```

   Explanation:
   The `head` command is used to display the first part of one or more files. By default, it shows the first 10 lines of each file, but you can customize the output using various options.

* `tail`: output the last part of files

   Terminal View:
   ```plaintext
   tail [options] [file1] [file2] ...
   ```

   Explanation:
   The `tail` command is used to display the last part of one or more files. By default, it shows the last 10 lines of each file, but you can customize the output using various options.


== System

* `date`: print the date and time

   Terminal View:
   ```plaintext
   date
   ```

   Explanation:
   The `date` command is used to display the current date and time in the system's configured format.

* `cal`: display a calendar

   Terminal View:
   ```plaintext
   cal [options]
   ```

   Explanation:
   The `cal` command is used to display a calendar. By default, it shows the current month's calendar, but you can specify options to view different months or years.

* `lsblk`: list connected drives

   Terminal View:
   ```plaintext
   lsblk [options]
   ```

   Explanation:
   The `lsblk` command is used to list all connected block devices, such as hard drives and SSDs. It provides information about the device names, their

 sizes, and the partition structure.


== Users

* `passwd`: change user password

   Terminal View:
   ```plaintext
   passwd [options] [username]
   ```

   Explanation:
   The `passwd` command is used to change a user's password. You need appropriate privileges to change passwords for other users. By default, it changes the password for the current user if no username is specified.

* `usermod`: modify a user account

   Terminal View:
   ```plaintext
   usermod [options] [username]
   ```

   Explanation:
   The `usermod` command is used to modify user account properties. It allows you to change various attributes such as the user's home directory, shell, user ID, group ID, and more.

* `groupadd`: create a new group

   Terminal View:
   ```plaintext
   groupadd [options] [groupname]
   ```

   Explanation:
   The `groupadd` command is used to create a new group. You can specify the group name as an argument, and the command will create the group with the next available group ID.

* `whoami`: print current logged user

   Terminal View:
   ```plaintext
   whoami
   ```

   Explanation:
   The `whoami` command is used to print the username of the currently logged-in user.


== Permissions

* `sudo`: execute a command as another user

   Terminal View:
   ```plaintext
   sudo [command]
   ```

   Explanation:
   The `sudo` command is used to execute a command with superuser (root) privileges. It allows authorized users to perform administrative tasks that require elevated permissions.

* `su`: change the current user

   Terminal View:
   ```plaintext
   su [username]
   ```

   Explanation:
   The `su` command is used to switch to another user account. By default, it switches to the root user if no username is specified. You need the root user's password or appropriate privileges to switch to other user accounts.

* `chmod`: change file permissions

   Terminal View:
   ```plaintext
   chmod [options] mode [file1] [file2] ...
   ```

   Explanation:
   The `chmod` command is used to change the permissions of files and directories. It allows you to modify the read, write, and execute permissions for the owner, group, and other users.

* `chown`: change the owner of a file

   Terminal View:
   ```plaintext
   chown [options] owner[:group] [file1] [file2] ...
   ```

   Explanation:
   The `chown` command is used to change the ownership of files and directories. You can specify the new owner and group using the appropriate options. Only the owner or a privileged user can change the ownership.

* `chgrp`: change the group of a file

   Terminal View:
   ```plaintext
   chgrp [options] group [file1] [file2] ...
   ```

   Explanation:
   The `chgrp` command is used to change the group ownership of files and directories. You need appropriate privileges to change the group.


== Compression

* `tar`: archive files

   Terminal View:
   ```plaintext
   tar [options] [archive] [files/directories]
   ```

   Explanation:
   The `tar` command is used to create or extract tar archives. It can combine multiple files and directories into a single archive file or extract the contents of an existing archive.

* `gzip`: compress and expand files

   Terminal View:
   ```plaintext
   gzip [options] [file1] [file2] ...
   ```

   Explanation:
   The `

gzip` command is used to compress files. It reduces the file size and creates a compressed version with the extension ".gz". You can also use it to decompress ".gz" files and restore the original files.


== Remote

* `ssh`: remote login

   Terminal View:
   ```plaintext
   ssh [options] [user@]hostname
   ```

   Explanation:
   The `ssh` command is used to establish a secure remote login to another machine over a network. You can specify the username and hostname of the remote machine to initiate the connection.

* `rsync`: remote file copying tool

   Terminal View:
   ```plaintext
   rsync [options] source [destination]
   ```

   Explanation:
   The `rsync` command is used to efficiently synchronize and copy files between local and remote systems. It only transfers the differences between the source and destination files, minimizing network usage.


== Process management

* `ps`: report process status

   Terminal View:
   ```plaintext
   ps [options]
   ```

   Explanation:
   The `ps` command is used to report information about active processes running on the system. It provides details such as process IDs (PIDs), resource utilization, and relationships between processes.

* `kill`: stop a process

   Terminal View:
   ```plaintext
   kill [options] [PID]
   ```

   Explanation:
   The `kill` command is used to send signals to processes, allowing you to terminate or manipulate their behavior. By default, it sends the SIGTERM signal to gracefully terminate a process.

* `top`: display list of running processes

   Terminal View:
   ```plaintext
   top
   ```

   Explanation:
   The `top` command is used to monitor the real-time system activity. It displays an interactive list of running processes, resource usage, and system information. Pressing 'q' will exit the command.

* `htop`: improved version of `top`

   Terminal View:
   ```plaintext
   htop
   ```

   Explanation:
   The `htop` command is an improved version of `top`. It provides an interactive process viewer with a more user-friendly interface and additional features for monitoring and managing processes.

* `bg`: put a process on the background

   Terminal View:
   ```plaintext
   bg [job_spec]
   ```

   Explanation:
   The `bg` command is used to move a stopped or suspended job to the background, allowing it to continue running while you work on other tasks.

* `fg`: bring a process on the foreground

   Terminal View:
   ```plaintext
   fg [job_spec]
   ```

   Explanation:
   The `fg` command is used to bring a background job to the foreground, allowing you to interact with it directly.


== Package manager

* `apt-get`

   Terminal View:
   ```plaintext
   apt-get [options] [command]
   ```

   Explanation:
   The `apt-get` command is a package management tool used in Debian-based systems, such as Ubuntu. It allows you to install, update, and remove software packages from the system.

* `pacman`

   Terminal View:
   ```plaintext
   pacman [options] [command]
   ```

   Explanation:
   The `pacman` command is a package management tool used in Arch Linux and its derivatives. It allows you to install, update, and remove software packages from the system.

* `pip`

   Terminal View:
   ```plaintext
   pip [options] [command]
   ```

   Explanation:
   The `pip` command is a package management tool for Python. It is used to install, upgrade, and manage Python packages and their dependencies.

* `npm`



   Terminal View:
   ```plaintext
   npm [command]
   ```

   Explanation:
   The `npm` command is a package manager for Node.js. It allows you to install, update, and manage JavaScript packages and libraries.

* `composer`

   Terminal View:
   ```plaintext
   composer [command]
   ```

   Explanation:
   The `composer` command is a dependency management tool for PHP. It is used to install, update, and manage PHP packages and their dependencies.


== Text editor

* `vim`

   Terminal View:
   ```plaintext
   vim [file]
   ```

   Explanation:
   The `vim` command is a powerful text editor available in most Unix-like systems. It provides a full-featured editing environment with various modes and commands for efficient text manipulation.

* `nvim`

   Terminal View:
   ```plaintext
   nvim [file]
   ```

   Explanation:
   The `nvim` command is an improved version of the Vim text editor. It offers better performance, extensibility, and additional features while maintaining compatibility with Vim.

* `nano`

   Terminal View:
   ```plaintext
   nano [file]
   ```

   Explanation:
   The `nano` command is a user-friendly text editor for Unix-like systems. It provides a simple and intuitive interface for editing files without requiring extensive knowledge of text editing commands.
