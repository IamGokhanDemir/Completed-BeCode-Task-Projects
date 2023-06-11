

# Finding Files with Linux

To complete the exercise, follow the instructions below:

## Connect to the virtual machine

Connect to the virtual machine with the following credentials:

- **IP**: 10.12.181.X
- **User**: student
- **Password**: student

## Find, Locate, and Which

### Locate

The `locate` command allows you to find a file quickly by searching a database of existing files. However, the database may not include recently created files or directories. To update the database, use the `updatedb` command. The syntax for using `locate` is as follows:

```sh
$ locate filename
```

Explanation: This command searches the database for the given filename and returns the paths of all matching files.

### Find

The `find` command searches for files within the directory tree. You can specify the directory to search in, or use `/` to search the entire tree. To search in the current directory, use `.`. The syntax for using `find` is as follows:

```sh
$ find directory -name file_name
```

Explanation: This command recursively searches for files with the specified name within the given directory.

To search for a directory, use the following syntax:

```sh
$ find directory -type d -name directory_name
```

Explanation: This command searches for directories with the specified name within the given directory.

Please note that the binary file's directory must be specified in the `PATH` variable for the command to work.

### Which

The `which` command is used to locate the executable file associated with a given command by searching the `PATH` environment variable. It returns one of the following status codes:

- 0: If all specified commands are found and executable.
- 1: If one or more specified commands are nonexistent or not executable.
- 2: If an invalid option is specified.

To use `which`, simply provide the command as an argument. For example:

```sh
$ which whoami
> /usr/bin/whoami
```

Explanation: This command searches for the executable file associated with the `whoami` command and returns its path.

The `PATH` variable must include the directory where the binary file is located for the command to work.

## Exercises

1. Create a file named `my-file.txt` using the `touch` command. Then, execute the `locate my-file.txt` command. Do you find the file?
   > Your response: No

   Explanation: The `touch` command creates an empty file with the specified name. The `locate` command then searches the database for the file. If the file is found, its path will be displayed.

   Command: 
   ```sh
   $ touch my-file.txt
   $ locate my-file.txt
   ```

2. Run the command `sudo updatedb`, and run the `locate my-file.txt` command again. Do you find your file?
   > Your response: Yes

   Explanation: Running `sudo updatedb` updates the locate database, ensuring that newly created files are included in the search. Running `locate my-file.txt` again should now find the file.

   Command: 
   ```sh
   $ sudo updatedb
   $ locate my-file.txt
   ```

3. Use the `which` command to find the executable file `nc` and indicate the path.
   > Path: /bin/nc

   Explanation: The `which` command searches for the executable file associated with the specified command and returns its path.

   Command: 
   ```sh
   $ which nc
   ```

4. Use the `which` command to find the executable file `becode`. What is the flag?
   > Flag: BC{WH1CH_FL4G_EXECUTLE_FILE}

   Explanation: the `which` command helps you determine the location of the executable file (`becode` in this case) by searching for it in the directories specified in the `PATH` environment variable. This is useful when you want to know the full path to the command's executable file.

   Command: 
	 1. When you execute the command `which becode`, it searches for the executable file associated with the command `becode`.
    
	 1. The command checks the directories listed in the `PATH` environment variable one by one to find the first occurrence of the executable file named `becode`.
    
	 1. If the executable file is found, the command prints the path to the file on the terminal.
    
	 1. If the executable file is not found or the command `becode` is not recognized, the command will not produce any output.
   ```sh
   $ which becode
   ```

5. Search for a file that contains the name "Edgar Allan Poe" using the `find` command. What is the flag?
   > Flag: BC{3d54r_4ll4n_P03_FL45}

   Explanation: The `find` command is used to search for files within the directory tree, the `find` command with the specified options searches for files with names containing the phrase "Edgar Allan Poe" starting from the root directory and displays the paths of any matching files found.

   Command:
	1. The command starts with `find` followed by the starting point of the search, indicated by `/`. This means the search will start from the root directory and traverse through all directories and subdirectories.
    
	1. The `-type f` option is used to specify that we are searching for files (as opposed to directories or other types of entries).
    
	1. The `-name "*Edgar Allan Poe*"` option specifies the pattern or name of the file we are searching for. In this case, it is looking for files with names that contain the phrase "Edgar Allan Poe". The asterisks (`*`) act as wildcards, allowing for any characters before and after the specified phrase.
    
	1. When the command is executed, it starts searching from the root directory (`/`) and looks for files that match the specified name pattern.
    
	1. If any files are found that match the pattern, their paths are printed on the terminal.

   permission denied what now?:  Because you cannot access  this file/folder in the command line due denied  access, you can work around it, one of the option is typing in the IP address in a browser of choice and then accessing the DevTools from the browser, in this case  you can find the FLAG in the elements tab
   ```sh
   $ find / -type f -name "*Edgar Allan Poe*"
   ```

6. Use the `find` command to locate the file `password.txt` and specify the flag.
   > Flag: BC{PASSWORD_FILE}

   Explanation: the `find` command with the specified options searches for files with the exact name "password.txt" starting from the root directory and displays the paths of any matching files found.

   Command: 
	1. The command starts with `find` followed by the starting point of the search, indicated by `/`. This means the search will start from the root directory and traverse through all directories and subdirectories.
    
	1. The `-type f` option is used to specify that we are searching for files (as opposed to directories or other types of entries).
    
	1. The `-name "password.txt"` option specifies the exact name of the file we are searching for. In this case, it is looking for a file named "password.txt".
    
	1. When the command is executed, it starts searching from the root directory (`/`) and looks for files with the exact name "password.txt".
    
	1. If any files are found that match the specified name, their paths are printed on the terminal.
   
   when running this code this results gives you a lot of files where access is denied. But looking in the list of denied files you find a file called (in this example) /var/www/html/a/b/c/d/e/g/h/i/j/k/l/m/n/o/p/q/r/s/t/u/v/w/x/y/z/password.txt. After finding this file you can use the cat command to read what is inside and find the flag.
   ```sh
   $ find / -type f -name "password.txt"
   ```

7. Use the `find` command to find a file that starts with `becode-` and ends with `.sh`.
   > Flag: BC{FLAG_FIND_PARTIAL_PATH}

   Explanation: 
	 - The command starts with `find` followed by the starting point of the search, indicated by `/`. This means the search will start from the root directory and traverse through all directories and subdirectories.
    
	- The `-type f` option is used to specify that we are searching for files (as opposed to directories or other types of entries).
    
	- The `-name "becode-*.sh"` option specifies the pattern of the file names we are searching for. In this case, it is looking for files with names starting with "becode-", followed by any characters, and ending with ".sh".
    
	- When the command is executed, it starts searching from the root directory (`/`) and looks for files that match the specified pattern.
    
	- If any files are found that match the pattern, their paths are printed on the terminal.
   
  In summary, the `find` command with the specified options searches for files with names matching the pattern "becode-*.sh" starting from the root directory and displays the paths of any matching files found.

   Command: This one is very easy, again you will get a list of permission denied files but if you look good you will find the FLAG between these list of directory/files
   ```sh
   $ find / -type f -name "becode-*.sh"
   ```

8. Use the `find` command to identify any file (not directory) modified in the last day, NOT owned by the root user, and execute `ls -l` on them. **Chaining/piping commands is NOT allowed!**
   > Your command: find / -type f -mtime -1 -not -user root -exec ls -l {} \; 2>/dev/null

   Explanation: By using this command, you can search for files that were modified within the last day, are not owned by the `root` user, and display detailed information for each file while excluding any permission denied errors from the output.


   Command: 
	 - `find /`: Initiates the `find` command and specifies the starting directory as the root directory (`/`).
	- `-type f`: Specifies that we are searching for regular files.
	- `-mtime -1`: Matches files that were modified within the last 24 hours. The `-1` represents the number of days. In this case, it's set to 1, indicating the previous day.
	- `-not -user root`: Matches files that are not owned by the `root` user. This filters out files owned by the `root` user.
	- `-exec ls -l {} \;`: Executes the `ls -l` command on each matched file and displays detailed file information. The `{}` placeholder represents the matched file.
	- `2>/dev/null`: Redirects the error output (stderr) to `/dev/null`. This ensures that any permission denied errors or other error messages are discarded and not displayed in the output.
   ```sh
   $ find / -type f -mtime -1 -not -user root -exec ls -l {} \; 2>/dev/null

   ```

9. Use the `find` command to find all files that have an authorization of `0777`.
   > Your command: 

   Explanation: The `find` command is used to search for files within the directory tree. In this case, we are searching for files with the specified permission (`-perm 0777`).

   Command: 
   ```sh
   $ find / -type f -perm 0777
   ```

10. Use the `find` command to find all files in the folder `/home/student/findme/` that have an authorization of `0777` and change the permissions of these files to `0755`.
    > Your command: 

    Explanation: The `find` command is used to search for files within the specified directory. We are looking for files with the specified permission (`-perm 0777`) and then using `-exec chmod 0755 {} \;` to change the permissions of each file found.

    Command: 
    ```sh
    $ find /home/student/findme/ -type f -perm 0777 -exec chmod 0755 {} \;
    ```