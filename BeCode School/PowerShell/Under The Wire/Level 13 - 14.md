
The password for Century14 is the number of words within the file on the desktop.

## Solution

This password is easy to find with the following command in the desktop folder  `Get-ChildItem | get-content | Measure-Object -Word`, after this command we see that we get the number `755` what is the password for the next level

```
PS C:\users\century13\desktop> Get-ChildItem


    Directory: C:\users\century13\desktop


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/30/2018   3:38 AM           7894 countm
                                                 ywords


PS C:\users\century13\desktop> Get-ChildItem | get-conte
nt | Measure-Object -Word

Lines Words Characters Property
----- ----- ---------- --------
        755
```

## Conclusion
We only had the use the `Get-ChildItem | get-content | Measure-Object -Word`, command in the desktop folder to find the password. When in the user directory we can use the `Get-ChildItem .\Desktop | get-content | Measure-Object -Word`. To look in the Desktop folder.

#### Result

```
password: 755
user login command: ssh century14@century.underthewire.tech
```

### Here's an explanation of the command and its logic:

The command `Get-ChildItem | Get-Content | Measure-Object -Word` explained:

```powershell
Get-ChildItem | Get-Content | Measure-Object -Word
```

This command performs the following actions:

1. `Get-ChildItem`: Retrieves a list of files and directories in the current directory.

2. `|`: The pipe symbol (`|`) is used to pass the output of the previous command as input to the next command.

3. `Get-Content`: Reads the contents of each file passed from `Get-ChildItem` and outputs the content as text.

4. `|`: Another pipe symbol is used to pass the content of each file to the next command.

5. `Measure-Object -Word`: Calculates various statistics about the input text, specifically counting the number of words. The `-Word` parameter specifies that we want to count the words.

The logic of this command involves listing all files and directories in the current directory using `Get-ChildItem`, reading the contents of each file using `Get-Content`, and then using `Measure-Object` to count the number of words in the content. By executing this command, you will obtain the total count of words in all files in the current directory.