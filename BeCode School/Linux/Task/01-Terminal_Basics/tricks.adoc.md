
# Tricks

This file is just a place to store useful/funny tricks in the terminal. If you have some, give them to your coach so that he/she can add them.

## Cheat sheet

If you ever need some quick online documentation on the command line, give a try to [cheat.sh](https://github.com/chubin/cheat.sh). It's a repository of cheat sheets, where you can find information about commands, technologies, and more. You can access it using `curl` or with a specific command line utility called `cht.sh`.

### Examples

Here are a few examples of how you can use `cheat.sh`:

1. To get a cheat sheet for Markdown, type:
   ```
   curl cheat.sh/markdown
   ```

2. To get a cheat sheet for Python loops, type:
   ```
   curl cheat.sh/python/loop
   ```

## Additional Useful Tricks

Here are 10 more useful tricks for the terminal along with explanations and easy-to-copy/paste commands:

1. **View the contents of a file:** To display the contents of a file in the terminal, use the `cat` command. For example:
   ```
   cat filename.txt
   ```

2. **Count the number of lines, words, and characters in a file:** The `wc` command can be used to count the number of lines, words, and characters in a file. For example:
   ```
   wc filename.txt
   ```

3. **Search for a specific text in files:** Use the `grep` command to search for a specific text pattern in one or multiple files. For example:
   ```
   grep "pattern" filename.txt
   ```

4. **Redirect command output to a file:** You can redirect the output of a command to a file using the `>` symbol. For example:
   ```
   command > output.txt
   ```

5. **Chain commands together:** Use the `&&` symbol to chain multiple commands together. Each command will execute if the previous one succeeds. For example:
   ```
   command1 && command2
   ```

6. **Navigate to the previous directory:** To quickly switch to the previous directory you were in, use the `cd -` command.

7. **Create a backup of a file:** Make a copy of a file before modifying it using the `cp` command. For example:
   ```
   cp filename.txt filename_backup.txt
   ```

8. **Repeat the last command with root privileges:** If you forgot to run a command with root privileges, you can rerun it using `sudo !!`. This will repeat the last command with `sudo`.

9. **Clear the terminal screen:** To clear the terminal screen, simply type `clear` and press Enter. This can be useful when the screen gets cluttered.

10. **Run a command in the background:** If you want to run a command in the background and continue using the terminal, append `&` at the end of the command. For example:
    ```
    command &
    ```

Certainly! Here are the commands with improved formatting for easy copy/paste:

11. **Create a new directory and navigate into it:**
   - Explanation: This command creates a new directory and then navigates into it, allowing you to quickly switch to a newly created directory.
   - Example command: 
     ```
     mkdir new_directory && cd new_directory
     ```

12. **Search for a file or directory:**
   - Explanation: This command searches for a specific file or directory within a given path. Replace "/path/to/search" with the actual path you want to search and "filename" with the name of the file or directory you're looking for.
   - Example command: 
     ```
     find /path/to/search -name "filename"
     ```

13. **Rename multiple files with a pattern:**
   - Explanation: This command renames multiple files at once by replacing a specific pattern in their names. Replace "old_pattern" with the pattern you want to replace and "new_pattern" with the desired new pattern.
   - Example command: 
     ```
     rename 's/old_pattern/new_pattern/' *
     ```

14. **Download a file from the internet:**
   - Explanation: This command downloads a file from a specified URL using the curl utility. Replace "URL_of_the_file" with the actual URL of the file you want to download.
   - Example command: 
     ```
     curl -O URL_of_the_file
     ```

15. **Monitor system resource usage:**
   - Explanation: The "top" command displays real-time information about system resource usage, including CPU usage, memory usage, and running processes. It's useful for monitoring system performance.
   - Example command: 
     ```
     top
     ```

6. **Calculate the size of a directory:**
   - Explanation: This command calculates the total size of a directory, including its subdirectories, and displays it in a human-readable format. Replace "directory_name" with the name of the directory you want to measure.
   - Example command: 
     ```
     du -sh directory_name
     ```

17. **Create a compressed archive (tarball) of a directory:**
   - Explanation: This command creates a compressed archive of a directory using the tar utility. The "-czvf" options specify the compression method (gzip), the archive filename, and the directory to be archived.
   - Example command: 
     ```
     tar -czvf archive.tar.gz directory_name
     ```

18. **Extract files from a compressed archive (tarball):**
   - Explanation: This command extracts files from a compressed archive created with tar. The "-xzvf" options specify the extraction method (gzip), the archive filename, and the location to extract the files to.
   - Example command: 
     ```
     tar -xzvf archive.tar.gz -C destination_directory
     ```

19. **Create a secure encrypted zip archive:**
   - Explanation: This command creates a zip archive of a file or directory and encrypts it with a password. Replace "archive.zip" with the desired name of the encrypted archive and "file.txt" with the file or directory you want to encrypt.
   - Example command: 
     ```
     zip -e archive.zip file.txt
     ```

20. **Monitor real-time log files:**
    - Explanation: The "tail -f" command displays the last few lines of a file in real-time and continuously updates the output as new lines are added. It's commonly used to monitor log files and track ongoing activities.
    - Example command: 
      ```
      tail -f log_file.txt
      ```

Feel free to explore these tricks and experiment with different commands to enhance your productivity and efficiency in the terminal.