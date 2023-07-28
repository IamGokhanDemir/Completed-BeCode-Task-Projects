
The password for Century7 is the number of folders on the desktop.


## Solution

To find the next password you just have to count the folders in the desktop directory. There 2 ways achieving this.

```
ls: You can us the ls command and manualy count all the folders

(Get-ChildItem -Directory).Count: This command counts automatically all the folders in the directory you currently in.

```

## Result output command

```
PS C:\users\century6\desktop> (Get-ChildItem -Directory).Count
197
```

## Conclusion

After running the `(Get-ChildItem -Directory).Count` command you can see the next password that is the number `197`

#### Result

```
password: 197
user login command: ssh century7@century.underthewire.tech
```

### Here's an explanation of the command and its logic:

To count the number of folders in the current directory using a single command in PowerShell, you can use the following command:

```powershell
(Get-ChildItem -Directory).Count
```


1. `Get-ChildItem`: This cmdlet is used to retrieve the child items (files and folders) within the current directory.

2. `-Directory`: This parameter filters the results to only include directories (folders).

3. `(Get-ChildItem -Directory)`: This part of the command retrieves all the directories within the current directory.

4. `.Count`: This property returns the count of the items in the collection, which in this case represents the number of folders in the current directory.

Executing this command in PowerShell will provide you with the count of folders in the current directory.