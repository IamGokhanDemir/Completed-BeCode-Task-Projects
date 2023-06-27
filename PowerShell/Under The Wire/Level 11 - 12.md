
The password for Century12 is the name of the hidden file within the contacts, desktop, documents, downloads, favorites, music, or videos folder in the user’s profile.  
  
**NOTE:**  
– Exclude “desktop.ini”.  
– The password will be lowercase no matter how it appears on the screen.

## Solution

The password for the next level is in hidden so the `ls` command will not work in this case. We first exit the the desktop folder using the `cd ..` command and then we type the following command ````
Get-ChildItem | Get-ChildItem -Recurse -File -Hidden | Where-Object {$_.Name -ne 'desktop.ini'}

```
PS C:\users\century11\desktop> cd ..
PS C:\users\century11> Get-ChildItem | Get-ChildItem -Re
curse -File -Hidden | Where-Object {$_.Name -ne 'desktop
.ini'}


    Directory: C:\users\century11\Downloads


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
--rh--        8/30/2018   3:34 AM             30 secret
                                                 _sauce
```

## Conclusion 

After running the `Get-ChildItem | Get-ChildItem -Recurse -File -Hidden | Where-Object {$_.Name -ne 'desktop.ini'}`  we see the password `secret_sauce` under Name in  the downloads folder

#### Result

```
password: secret_sauce
user login command: ssh century12@century.underthewire.tech
```

### Here's an explanation of the command and its logic:

The command `Get-ChildItem | Get-ChildItem -Recurse -File -Hidden | Where-Object {$_.Name -ne 'desktop.ini'}` explained:

```
Get-ChildItem | Get-ChildItem -Recurse -File -Hidden | Where-Object {$_.Name -ne 'desktop.ini'}
```

This command performs the following actions:

1. `Get-ChildItem`: Retrieves a list of child items (files and directories) in the current location.

2. `|`: Passes the output of the previous command as input to the next command.

3. `Get-ChildItem -Recurse -File -Hidden`: Operates on each item obtained from the previous `Get-ChildItem` command. It recursively retrieves only files (`-File`) that are hidden (`-Hidden`).

4. `|`: Passes the output of the previous `Get-ChildItem` command to the next command.

5. `Where-Object {$_.Name -ne 'desktop.ini'}`: Filters the items based on a condition specified within the script block (`{}`). It checks if the `Name` property of each item is not equal (`-ne`) to `'desktop.ini'`. Items that meet this condition are passed through the pipeline.

The command's logic involves retrieving child items, including hidden files, and then filtering out any item with the name `'desktop.ini'`. By executing this command, you will obtain a list of hidden files (excluding 'desktop.ini') within the child items of the current directory, including subdirectories.