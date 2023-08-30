
# Permissions

**Type of challenge:** Learning

**Duration:** 30 min

**Team challenge:** Solo

## Learning objectives

By the end of this challenge, you should be able to:

- Execute a command as root
- Check the permissions of a file
- Change the permissions of a file
- Change the owner of a file
- Change the group of a file

## Requirements

This briefing assumes that you know how to:

- Consult the manual within the terminal
- Create and read files in the terminal
- List the contents of a directory

## The mission

You've heard of four new tools to manage permissions and execute commands with administrative rights: `sudo`, `chmod`, `chown`, and `chgrp`. Open your terminal and read their manuals to understand them, then follow the instructions below.

## Instructions

1. **Create a file**: Use the `touch` command to create a new file. The `touch` command updates the access and modification timestamps of a file or creates a new empty file if it doesn't exist.

   ```bash
   touch filename
   ```

   Replace "filename" with the desired name of your file.

2. **Check the owner and group of the file**: Use the `ls` command with the `-l` option to display detailed information about the file, including its owner and group.

   ```bash
   ls -l filename
   ```

   This command will show the file's permissions, owner, group, size, and modification timestamp.

3. **Change the owner of the file to root**: Use the `chown` command to change the owner of the file to the root user. The `chown` command stands for "change owner".

   ```bash
   sudo chown root filename
   ```

   The `sudo` command is used to execute a command as the superuser (root) in order to change the owner of the file.

4. **Change the group of the file to root**: Use the `chgrp` command to change the group of the file to the root group. The `chgrp` command stands for "change group".

   ```bash
   sudo chgrp root filename
   ```

   Again, the `sudo` command is used to execute the command with administrative privileges.

5. **Check the file's permissions**: Use the `ls` command with the `-l` option to verify the file's permissions.

   ```bash
   ls -l filename
   ```

   The output will show the permissions in a symbolic format (e.g., -rwxr-xr--), where each character represents read (`r`), write (`w`), or execute (`x`) permission for the owner, group, and others.

6. **Give all rights to owner and group, but none to others**: Use the `chmod` command to set the file's permissions, granting read, write, and execute permissions to the owner and group, while denying all permissions to others.

   ```bash
   sudo chmod ug=rwx,o= filename
   ```

   In this command, `ug=rwx` sets the read, write, and execute permissions for the owner (`u`) and group (`g`), while `o=` removes all permissions for others.

7. **Try to print the file on screen**: Use the `cat` command to attempt printing the contents of the file.

   ```bash
   cat filename
   ```

   The `cat` command is used to concatenate and display the contents of files. However, without the necessary permissions, an error message will be displayed.

8. **Print the file with root privileges**: Use the `sudo` command with `cat` to print the contents of

 the file with root privileges.

   ```bash
   sudo cat filename
   ```

   The `sudo` command allows executing a command with administrative rights, bypassing the file permissions and displaying the contents of the file.

## Resources

- [File Permissions](https://www.linux.com/training-tutorials/understanding-linux-file-permissions/)
- [Introduction to Linux Permissions](https://www.pluralsight.com/blog/it-ops/linux-file-permissions)