
The password for Century4 is the number of files on the desktop.


## Solution

To find the next password you have to look into the files using the following command. There 2 ways.
```
ls: This will display all the files in that directory and then you can count them one by one

ls | Measure-Object -Property Length -Sum | Select-Object -ExpandProperty Count: This command wil only display the ammount of files listed in the directory which makes it easier to count
```

## Result output command

```
PS C:\users\century3\desktop> ls | Measure-Object -Prope
rty Length -Sum | Select-Object -ExpandProperty Count
123
```

## Conclusion

After running `PS C:\users\century3\desktop> ls | Measure-Object -Property Length -Sum | Select-Object -ExpandProperty Count` command we get the result of `123` files.

#### Result
```
password: 123
user login command: ssh century4@century.underthewire.tech
```


### Here's an explanation of the command and its logic:

1. **`ls`**: This command lists the files and directories in the current directory.

2. **`|` (Pipe Operator)**: The pipe operator takes the output from the previous command (`ls`) and passes it as input to the next command (`Measure-Object`).

3. **`Measure-Object`**: This cmdlet calculates various statistics of the input objects. In this command, we use it to measure the length (size) of the files.

4. **`-Property Length`**: This parameter specifies the property of the input objects (files) that we want to measure, which in this case is the "Length" property representing the file size.

5. **`-Sum`**: This parameter tells `Measure-Object` to calculate the sum of the lengths of all the files.

6. **`|` (Pipe Operator)**: Again, the pipe operator takes the output from the previous command (`Measure-Object`) and passes it as input to the next command (`Select-Object`).

7. **`Select-Object`**: This cmdlet selects specific properties of the input objects. In this command, we use it to select the "Count" property, which represents the number of files.

8. **`-ExpandProperty Count`**: This parameter instructs `Select-Object` to return the value of the "Count" property directly, instead of wrapping it in a custom object.

In summary, the command `ls | Measure-Object -Property Length -Sum | Select-Object -ExpandProperty Count` lists the files and directories in the current directory, calculates the sum of the lengths of the files, and then selects and displays the count of files.