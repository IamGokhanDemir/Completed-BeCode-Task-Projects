

The password for Century10 is the **161st** word within the file on the desktop.  
  
**NOTE:**  
– The password will be lowercase no matter how it appears on the screen.

## Solution

After listing what's in the desktop directory using the `ls` command we find the `Word_File.txt` , file, when we  `cat` the txt file we find many words and we need the 161st word as the password. Therefore we use the following command: `(Get-Content -Path "C:\users\century9\desktop\Word_File.txt" -Raw | Select-String -Pattern '\b\w+\b' -AllMatches).Matches[160].Value` this command will print in our case  the 161st word that we need:

```
PS C:\users\century9\desktop> ls


    Directory: C:\users\century9\desktop


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/30/2018   3:34 AM           2131 Word_F
                                                 ile.tx
                                                 t


PS C:\users\century9\desktop> (Get-Content -Path "C:\use
rs\century9\desktop\Word_File.txt" -Raw | Select-String
-Pattern '\b\w+\b' -AllMatches).Matches[160].Value
pierid
```

## Conclusion 

After running the `(Get-Content -Path "C:\users\century9\desktop\Word_File.txt" -Raw | Select-String -Pattern '\b\w+\b' -AllMatches).Matches[160].Value` command we can see that the 161st word is `pierid` and our password for the next level

#### Result

```
password: pierid
user login command: ssh century10@century.underthewire.tech
```

### Here's an explanation of the command and its logic:



```powershell
(Get-Content -Path "C:\users\century10\desktop\filename.txt" -Raw | Select-String -Pattern '\b\w+\b' -AllMatches).Matches[160].Value
```

Make sure to replace `"C:\users\century10\desktop\filename.txt"` with the actual path and filename of the file on your desktop. Number 160 can be change with another number that is required 

Let's break down the command:

1. `(Get-Content -Path "C:\users\century10\desktop\filename.txt" -Raw | Select-String -Pattern '\b\w+\b' -AllMatches)`: This part of the command reads the content of the text file specified by the path and filename using the `Get-Content` cmdlet. The `-Raw` parameter ensures that the entire content is read as a single string. The output is then piped (`|`) to `Select-String` cmdlet with the pattern `\b\w+\b`, which matches each word in the text file. The `-AllMatches` parameter ensures that all matches are selected.

2. `.Matches[160].Value`: The `.Matches` property is used to access the collection of matches found by `Select-String`. Since PowerShell arrays are zero-indexed, `[160]` retrieves the 161st match (word) from the collection. Finally, `.Value` is used to extract the actual word from the match.

By executing this command, you will obtain the password for Century10, which corresponds to the 161st word within the specified text file.