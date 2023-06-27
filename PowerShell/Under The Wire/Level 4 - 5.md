
The password for Century5 is the name of the file within a directory on the desktop that has spaces in its name.  
  
**NOTE:**  
– The password will be lowercase no matter how it appears on the screen.

## Solution

To find the next password we start with the `ls` command to list the files and directories in the directory
```
PS C:\users\century4\desktop> ls


    Directory: C:\users\century4\desktop


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        6/23/2022  10:30 PM                Can
                                                 you
                                                 open
                                                 me
d-----        2/27/2023   4:55 PM                file
d-----         2/8/2022  10:35 PM                Open.t
                                                 xt
-a----        6/17/2022   1:19 AM              0 Folder
                                                 List
```

## Result output commands:

Here we find the the directory `Can you open me` we select this one because this one has spaces in its name like mentioned in the challenge. We enter this directory using de `cd` command and list what's inside again using the `ls` command.

```
#first we enter the directory 
PS C:\users\century4\desktop> cd "Can you open me"
#then we list what's inside
PS C:\users\century4\desktop\Can you open me> ls


    Directory: C:\users\century4\desktop\Can you open
    me


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        6/23/2022  10:24 PM             24 49125
```

## Conclusion

After entering the `Can you open me` amd listing what inside using the `ls` command we can find or next password `49125` under Name

### result

```
password: 49125
user login command: ssh century5@century.underthewire.tech
```

### Here's an explanation of the command and its logic:

The command `cd "Can you open me"` is used to change the current directory in PowerShell to a directory named "Can you open me" on the desktop.

- `cd` is the shorthand for the `Set-Location` cmdlet, which is used to change the current location (or directory) in PowerShell.

- `"Can you open me"` is enclosed in double quotes to indicate that it is a single argument, even though it contains spaces. The quotes ensure that the entire directory name is treated as a single string.

- When you execute the command, PowerShell will attempt to change the current directory to "Can you open me" under the current path (`C:\users\century4\desktop` in this case).

- The command's logic is straightforward: By using the `cd` command followed by the directory name, you are instructing PowerShell to navigate to the specified directory. The quotes around the directory name ensure that spaces within the name are treated as part of the name rather than as separators.

- After executing the command, the current directory will be changed to `C:\users\century4\desktop\Can you open me`. You can then perform further operations or list the files within this directory.