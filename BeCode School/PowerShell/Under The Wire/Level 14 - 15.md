
The password for Century15 is the number of times the word “polo” appears within the file on the desktop.  
  
**NOTE:**  
– You should count the instances of the **whole word** only..

## Solution

To find the final password we have to count the amount of "polo" that appears in the the on the desktop. To able to do that with one command we use this command `(Get-ChildItem | Get-Content | Select-String -Pattern "\bpolo\b" -AllMatches | ForEach-Object {$_.Matches}).Count` and get as result `153`

```
PS C:\users\century14\desktop> (Get-ChildItem | Get-Cont
ent | Select-String -Pattern "\bpolo\b" -AllMatches | Fo
rEach-Object {$_.Matches}).Count
153
```

## Conclusion

With this using this one command in this case in the Desktop folder we can immediately get the total amount of time the words `polo` appear in the file

#### Result

```
password: 153
user login command: ssh century15@century.underthewire.tech
```

### Here's an explanation of the command and its logic:


Command:
```powershell
(Get-ChildItem | Get-Content | Select-String -Pattern "\bpolo\b" -AllMatches | ForEach-Object {$_.Matches}).Count
```

Explanation:
1. `(Get-ChildItem | Get-Content`: This part of the command retrieves the content of files within the current directory using `Get-ChildItem` and reads the content of each file using `Get-Content`. This provides the input text for further processing.

2. `Select-String -Pattern "\bpolo\b" -AllMatches`: The `Select-String` cmdlet is used to search for occurrences of the word "polo" in the input text. The `-Pattern` parameter specifies the regular expression pattern to match. In this case, `"\bpolo\b"` is used to match the exact word "polo" with word boundaries. The `-AllMatches` parameter ensures that all occurrences of the pattern are selected.

3. `ForEach-Object {$_.Matches}`: The `ForEach-Object` cmdlet is used to iterate over the matches found by `Select-String`. `$_.Matches` accesses the collection of matches for each line of text.

4. `.Count`: Finally, the `.Count` property is used to count the number of matches found.

Logic:
This command counts the occurrences of the exact word "polo" and words containing "polo" within the files in the current directory. It searches through the content of each file, identifies the matches, and counts the total number of matches found.


