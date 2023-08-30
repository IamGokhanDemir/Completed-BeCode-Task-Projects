


The password for Century9 is the number of unique entries within the file on the desktop.

## Solution

After using the `ls` command you can find the `unique.txt` file with the entries. There are 2 ways to count the entries, you can use the `cat` command and count them manually or you can use the `(Get-Content -Path "filename.txt" | Measure-Object -Line).Lines` command to let powershell count the entries inside the txt file

```
PS C:\users\century8\desktop> ls


    Directory: C:\users\century8\desktop


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/30/2018   3:33 AM          15858 unique
                                                 .txt


PS C:\users\century8\desktop> (Get-Content -Path "unique
.txt" | Measure-Object -Line).Lines
696
```


## Conclusion 

After running the `(Get-Content -Path "unique.txt" | Measure-Object -Line).Lines` command we can see that we have `696` entries and is the password for the next level.


#### Result

```
password: 696
user login command: ssh century9@century.underthewire.tech
```

### Here's an explanation of the command and its logic:

To count the number of entries in a text file using a single command in PowerShell, you can use the `Measure-Object` cmdlet along with the `-Line` parameter. Here's the command:

```powershell
(Get-Content -Path "filename.txt" | Measure-Object -Line).Lines
```

Let's break down the command:

1. `(Get-Content -Path "filename.txt" | Measure-Object -Line)`: This part of the command reads the contents of the text file specified by `"filename.txt"` using the `Get-Content` cmdlet. The output is then piped (`|`) to the `Measure-Object` cmdlet with the `-Line` parameter. This calculates the number of lines in the text file.

2. `.Lines`: The `.Lines` property is used to retrieve the count of lines from the output of `Measure-Object`. It returns the total number of entries or lines in the text file.

By running this command, you will get the count of entries in the text file specified by `"filename.txt"`.