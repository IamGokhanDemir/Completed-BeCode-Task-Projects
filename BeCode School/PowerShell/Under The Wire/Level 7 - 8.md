
The password for Century8 is in a readme file somewhere within the contacts, desktop, documents, downloads, favorites, music, or videos folder in the user’s profile.  
  
**NOTE:**  
– The password will be lowercase no matter how it appears on the screen.

## Solution

To find the next password you to exit the current directory and look in the other directories one by one. You can do that first exiting the current directory using the `cd ..` command and then the `ls` command to list available directories under the user and repeat this process until you find the readme file in one of them. Once you find the file you can `cat` to read what's inside

```
cd .. : The `cd ..` command is used in PowerShell to change the current working directory to the parent directory (one level up) from the current directory.

`cd`: This is the command used to change the current working directory.

`cat`: This is the command used to display the contents of a file.
```

## Result output command

```
PS C:\users\century7\desktop> cd ..
PS C:\users\century7> ls


    Directory: C:\users\century7


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-r---        7/16/2016   1:23 PM                Desktop
d-r---        8/30/2018   3:10 AM                Documents
d-----         6/9/2023   4:04 AM                Downloads
d-r---        7/16/2016   1:23 PM                Favorites
d-r---        7/16/2016   1:23 PM                Links
d-r---        7/16/2016   1:23 PM                Music
d-r---        7/16/2016   1:23 PM                Pictures
d-----        7/16/2016   1:23 PM                Saved Games
d-r---        7/16/2016   1:23 PM                Videos


PS C:\users\century7> cd Documents
PS C:\users\century7\Documents> ls
PS C:\users\century7\Documents> cd ..
PS C:\users\century7> cd Downloads
PS C:\users\century7\Downloads> ls


    Directory: C:\users\century7\Downloads


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/25/2022  10:18 PM             17 LineNumbers.txt
-a----        8/30/2018   3:29 AM              7 Readme.txt


PS C:\users\century7\Downloads> cat Readme.txt
7points
```

## Conclusion

Once we search the directories we can find the `Readme.txt` in the `Downloads` folder where we the `cat` the txt file to able to read what's inside and find the password `7points`

#### Result
```
password: 7points
user login command: ssh century8@century.underthewire.tech
```


### Here's an explanation of the command and its logic:

The `cat` command is used in PowerShell to display the contents of a file. It stands for "concatenate" and is primarily used for displaying text files:

1. `cat`: This is the command used to display the contents of a file.

2. `filename`: The `filename` parameter is the name or path of the file you want to view the contents of. You can specify either a relative or absolute path to the file.

When you execute `cat filename` in PowerShell, the command will read the contents of the specified file and display them in the console window. This allows you to view the text content of files, such as text documents, scripts, or configuration files. The `cat` command can be helpful for inspecting the contents of files without opening them in a text editor.