
The password for Century11 is the **10th** and **8th** word of the Windows Update service description combined PLUS the name of the file on the desktop.  
  
**NOTE:**  
– The password will be lowercase no matter how it appears on the screen.  
– If the 10th and 8th word of the service description is “apple” and “juice” and the name of the file on the desktop is “88”, the password would be “applejuice88”.

## Solution

There 2 ways to find the file on the desktop. First using the `ls` command second using the `Get-ChildItem` command when you are in Desktop directory. The first part of the password is in the name windowsupdates.

```
PS C:\users\century10\desktop> ls


    Directory: C:\users\century10\desktop


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/30/2018   3:34 AM             43 110


PS C:\users\century10\desktop> Get-ChildItem


    Directory: C:\users\century10\desktop


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/30/2018   3:34 AM             43 110
```

## Conclusion 

After running the `ls` command or the `Get-ChildItem` command we see that the second part of the password is the number `110` and this we combine with windowsupdates

#### Result

```
password: windowsupdates110
user login command: ssh century11@century.underthewire.tech
```

### Here's an explanation of the command and its logic:

The `Get-ChildItem` cmdlet in PowerShell is used to retrieve a list of child items (files and directories) within a specified location.

Syntax:
```
Get-ChildItem [[-Path] <String[]>] [[-Filter] <String>] [-Recurse] [-Force] [-File] [-Directory]
```

- `Get-ChildItem`: This is the cmdlet that retrieves the child items.
- `-Path`: Specifies the path to the directory for which you want to retrieve the child items. If not specified, it defaults to the current location.
- `-Filter`: Allows you to specify a filter pattern to include specific files or directories. Only items that match the specified filter will be returned.
- `-Recurse`: Specifies whether to include child items in subdirectories recursively.
- `-Force`: Forces the cmdlet to retrieve hidden or system files and directories.
- `-File`: Retrieves only files, excluding directories.
- `-Directory`: Retrieves only directories, excluding files.

The logic behind the `Get-ChildItem` cmdlet is as follows:
1. If the `-Path` parameter is provided, the cmdlet retrieves child items from the specified directory.
2. If the `-Path` parameter is not provided, the cmdlet retrieves child items from the current location.
3. If the `-Filter` parameter is provided, the cmdlet filters the child items based on the specified pattern.
4. If the `-Recurse` parameter is used, the cmdlet includes child items from subdirectories recursively.
5. If the `-Force` parameter is used, the cmdlet retrieves hidden or system files and directories.
6. If the `-File` parameter is used, the cmdlet retrieves only files.
7. If the `-Directory` parameter is used, the cmdlet retrieves only directories.

By executing the `Get-ChildItem` cmdlet, you can retrieve a list of files and directories within a specified location or the current directory, optionally filtered by certain criteria.
