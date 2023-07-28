
The password for Century6 is the short name of the domain in which this system resides in **PLUS** the name of the file on the desktop.  
  
**NOTE:**  
– If the short name of the domain is “blob” and the file on the desktop is named “1234”, the password would be “blob1234”.  
– The password will be lowercase no matter how it appears on the screen.

## Solution

To find the next password we start with the `ls` command to list the files and directories in the directory
```
PS C:\users\century5\desktop> ls


    Directory: C:\users\century5\desktop


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/30/2018   3:29 AM             54 3347
```

## Result output command:

Here you already can find a piece of the password `3347` under Name

## Conclusion 

To complete the password you have to find the domain name, you can do that using the `whoami` command:

```
PS C:\users\century5\desktop> whoami
underthewire\century5
```

Here we see that the domain name is `underthewire` and now we can combine the previous password with this password.

### result

```
password: underthewire3347
user login command: ssh century6@century.underthewire.tech
```

### Here's an explanation of the command and its logic:


The `whoami` command is used in PowerShell to display the username of the currently logged-in user. It retrieves the information about the identity of the user running the command.

1. When you log into a system or open a PowerShell session, you are assigned a username that uniquely identifies you.

2. By executing the `whoami` command, it queries the operating system or the underlying authentication system to retrieve the username associated with the current user session.

3. The command then displays the username on the screen, providing you with a quick way to identify the user account you are currently logged in with.

The `whoami` command is useful in various scenarios, including system administration, troubleshooting, and scripting. It allows you to verify the user context under which a particular action or command is being executed, ensuring that you have the necessary permissions and access rights.
