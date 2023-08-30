
# Text Manipulation with Linux

To perform various text manipulation tasks in Linux, it's important to understand and use specific commands. In many cases, you'll have access only to a terminal on a remote machine via SSH, as graphical user interfaces may not be available. This section explores some of the advanced commands that can help you find files, folders, and search for text within files.

## Connect to the Virtual Machine

To begin, connect to the virtual machine using the following credentials:

- **IP**: 10.12.181.X
- **User**: student
- **Password**: student

## Advanced Commands

### `cat`

The `cat` command is essential for displaying the contents of one or more text files. To display the content of a file, use the following syntax:

```sh
$ cat file.txt
```

You can also concatenate multiple files using `cat` and redirect the output to a new file:

```sh
$ cat file1.txt file2.txt file3.txt > concatenation.txt
```

### `more` and `less`

Both `more` and `less` are interactive commands used to display text files. They allow you to navigate through the file, search for specific text, and more. The key difference is that `more` only allows forward movement, while `less` provides backward movement as well. To use `less`, simply type:

```sh
$ less long-text.txt
```

### `tail` and `head`

The `tail` command displays the last N lines of a file, while `head` displays the first N lines. You can specify the number of lines to display using the `-n` option:

```sh
# Display the last 2 lines of file.txt
$ tail -n 2 file.txt

# Display the first 2 lines of file.txt
$ head -n 2 file.txt

# Display the third and fourth lines of file.txt
$ head -n 4 file.txt | tail -n 2
# Equivalent to: $ cat file.txt | head -n 4 | tail -n 2

# Display a file from the second line
$ tail -n +2 file.txt
```

### `watch`

The `watch` command runs a given command at regular intervals and displays its output. This is useful for monitoring changes or updates. For example, you can use `watch` to check the size of a file over time:

```sh
$ watch du -sh my_file.txt
```

You can also use `watch` to observe real-time updates in a directory:

```sh
$ watch ls my_result_folder
```

### `split`

The `split` command divides a file into several sub-files. You can split by size (`-b`), number of output files (`-n`), or by lines (`-l`).

```sh
# Split my_big_file into files with a maximum size of 1024 KB
$ split -b 1024k my_big_file

# Split my_big_file into 10 files
$ split -n 10 my_big_file

# Split my_big_file into files with a maximum of 4 lines each
$ split -l 4 my_big_file
```

The `split` command creates sub-files with names like `xaa`, `xab`, `xac`, and so on, depending on the splitting criteria.

### `join`

The `join` command merges lines from two files based on common fields, with the default field being the first column. Here's an example:

```sh
$ cat testfile1
1 India
2 US
3 Ireland
4 UK
5 Canada

$ cat testfile2
1 NewDelhi
2 Washington
3 Dublin
4 London
5 Toronto

$ join testfile1 testfile2
1 India NewDelhi
2 US Washington
3 Ireland Dublin
4 UK London
5 Canada Toronto
```

### `paste`

The `paste` command concatenates lines from multiple files. Each line from the first file is paired with a corresponding line from subsequent files. Here's an example:

```sh
$ cat testfile1
1 India
2 US
3 Ireland
4 UK
5 Canada

$ cat testfile2
1 NewDelhi
2 Washington
3 Dublin
4 London
5 Toronto

$ paste testfile1 testfile2
1 India 1 NewDelhi
2 US    2 Washington
3 Ireland   3 Dublin
4 UK    4 London
5 Canada    5 Toronto
```

### Text patterns (regular expressions and wildcards)

Text patterns are a powerful way to express strings of characters in a clear, unambiguous, and concise manner. They are used for various purposes such as file or string search, replacing complex patterns, and handling multiple files simultaneously. There are two main types of text patterns: wildcards and regular expressions.

#### Wildcards

Wildcards are a simplified version of regular expressions and provide a shorter syntax. The most important wildcard character is `*`, which represents any character, zero or more times. Here are some examples:

- List files whose names end with ".txt":
  ```
  ls *.txt
  ```

- List files/directories whose names start with "my":
  ```
  ls my*
  ```

- List files/directories whose names contain "my":
  ```
  ls *my*
  ```

- List files/directories whose names do not start with 'a':
  ```
  ls [^a]*
  ```

#### Regular expressions

Regular expressions (regex or regexp for short) are more comprehensive than wildcards and are used in tools like sed, awk, grep, and many programming languages. There are three main categories of regular expressions: BRE (basic regular expression), ERE (extended regular expression), and PCRE (Perl Compatible Regular Expressions). All expressions written in basic form (BRE) can be understood by the other forms, while PCRE is the most complete implementation.

The major difference with wildcards is the interpretation of the `*` character. In regular expressions, it means the previous character repeated zero or more times. Here are some examples:

- Filter lines containing a string that starts with "ab" and is followed by a character:
  ```
  grep ab. file.txt
  ```

- Show commented lines of a BASH script:
  ```
  grep ^# script.sh
  ```

- Show lines that start with a lowercase letter:
  ```
  grep ^[a-z] file.txt
  ```

- Search for "grey" or "gray" in a string:
  ```
  echo grey | grep -E "gr(a|e)y"
  # Equivalent to
  echo grey | grep gr[ae]y
  ```

For more detailed explanations and resources about wildcards and regular expressions, you can refer to the LPI training courses and other documentation provided in the links.

### Filtering with `grep`

Grep is a powerful command line tool used for filtering lines based on specific criteria. It allows you to display only the lines that match a given pattern.

- Simple use of grep:
    ```sh
    # displays the lines of file.txt that contain "plop"
    grep "plop" file.txt
    # is equivalent to 
    cat file.txt | grep "plop"
    ```
    Explanation: In the first command, `grep "plop" file.txt`, it searches for the pattern "plop" in the file "file.txt" and displays all the lines that contain the pattern. In the second command, `cat file.txt | grep "plop"`, it uses the `cat` command to display the contents of "file.txt" and then pipes (`|`) the output to `grep` to filter and display only the lines that contain the pattern "plop".

- Start and end of line:
    ```sh
    # lines that start with "hello"
    grep "^hello" file.txt
    # lines that end with "goodbye"
    grep "goodbye$" file.txt
    ```
    Explanation: The first command `grep "^hello" file.txt` searches for lines in "file.txt" that start with the word "hello". The `^` symbol denotes the start of a line. The second command `grep "goodbye$" file.txt` searches for lines in "file.txt" that end with the word "goodbye". The `$` symbol denotes the end of a line.

- More complex examples:
    ```sh
    # lines that contain "hello" and "goodbye"
    grep "goodbye" file.txt | grep "hello"

    # lines that contain letters, spaces, or commas in parentheses
    grep "([a-z ,]*)" file.txt
    ```
    Explanation: In the first command, `grep "goodbye" file.txt | grep "hello"`, it searches for lines in "file.txt" that contain both the words "hello" and "goodbye". The output of the first `grep` command is piped to the second `grep` command for further filtering. In the second command, `grep "([a-z ,]*)" file.txt`, it searches for lines in "file.txt" that contain any sequence of lowercase letters, spaces, or commas within parentheses.

- Extended mode with `egrep`:
    ```sh
    # does not display commented and empty lines
    egrep -v "^#|^$" file.txt
    ```
    Explanation: The `egrep` command is used to perform pattern matching using extended regular expressions. In this example, `-v` is used to invert the matching, and `^#|^$` is the pattern. It matches lines that do not start with `#` (commented lines) or are empty (blank lines). The output displays lines from "file.txt" that don't match these patterns.

## Various tools (`cut`, `sort`, `wc`, `uniq`, `diff`, `sed`, `awk`)

There are several command-line tools available for text analysis. Here's an overview of each tool and its usage:

### cut
The `cut` command is used to isolate specific columns from each line of input content. It allows you to extract fields or columns based on a delimiter.

Example:
```sh
cut -d "," -f 2 file.txt
```
Explanation:
- `-d ","` specifies the column delimiter as a comma.
- `-f 2` selects the second column.
The command extracts the second column from "file.txt".

### uniq
The `uniq` command removes consecutive identical lines from input. It only removes duplicate lines that are consecutive. It is often used in conjunction with the `sort` command.

Example:
```sh
cat file.txt | uniq
```
Explanation:
The `uniq` command reads input from `file.txt` and removes consecutive duplicate lines. The output contains unique lines.

### sort
The `sort` command is used to sort lines in ascending or descending order.

Example:
```sh
sort file1 file2 | uniq
```
Explanation:
The `sort` command sorts the lines in `file1` and `file2` and pipes the output to `uniq`, removing consecutive duplicate lines from the sorted output.

### wc
The `wc` command is used to count the number of characters, words, or lines in a text.

Example:
```sh
sort -u file.txt | wc -l
```
Explanation:
The `sort -u` command sorts the lines in `file.txt` and removes duplicates. Then, the `wc -l` command counts the number of lines in the sorted and unique output.

### diff
The `diff` command compares files line by line and displays the differences between them.

Example:
```sh
diff file1.txt file2.txt
```
Explanation:
The `diff` command compares the contents of `file1.txt` and `file2.txt` and displays the differences between them.

### sed
The `sed` command is a stream editor used for filtering or transforming text.

Example:
```sh
sed 's/PATTERN/REPLACE/OPTIONS' file.txt
```
Explanation:
The `sed` command replaces the first occurrence of `PATTERN` in each line of `file.txt` with `REPLACE`. Use the `-i` option to apply the changes directly to the file.

### awk
The `awk` command is a scripting language for manipulating data and generating reports. It can process text based on patterns and actions defined by the user.

Example:
```sh
awk '/manager/ {print}' employee.txt
```
Explanation:
The `awk` command searches for lines containing the pattern "manager" in `employee.txt` and prints those lines.

Exercises:

1. Search all sequences containing "Loxondota" in `/home/student/lorem.txt`
   > Command: `grep -r "Loxondota" /home/student/lorem.txt`
	`Flag: BC{GREP_ME_LOREM_FL4G}`
2. Copy the file `/etc/passwd` to your home directory. Display the line starting with the username "student".
   > Your Commands: 
   > ```sh
   > cp /etc/passwd ~/passwd_copy
   > grep "^student:" ~/passwd_copy
   > ```

3. Display the lines in the `passwd` file starting with login names of 3 or 4 characters.
   > Command: `grep "^...\\|^...." /etc/passwd`

4. In the file `/home/student/sample.txt`, determine the number of different values in the first and second columns.
   > Command: ` cut -d " " -f 1 sample.txt | sort | uniq -c |
 sort -nr`

5. In the file `/home/student/sample.txt`, sort the values in the second column by frequency of occurrence.
   > Command: `cut -d " " -f 2 sample.txt | sort | uniq -c | sort -nr`

6. In the file `/home/student/iris.data`, change the column separator from comma to tab (apply changes to the file).
   > Command: `sed -i 's/,/\t/g' /home/student/iris.data`

7. In the file `/home/student/iris.data`, extract the values from the third column (petal length in cm) using `cut`.
   > Command: `cut -d "," -f 3 /home/student/iris.data`

8. In the file `/home/student/iris.data`, count the number of flower species using `cut` and `uniq`.
   > Command: `cut -d "," -f 5 /home/student/iris.data | sort | uniq | wc -l`

9. In the file `/home/student/iris.data`, sort the file by increasing petal length using `sort`.
   > Command: `sort -t "," -n -k 3 /home/student/iris.data`

10. In the file `/home/student/iris.data`, show only lines with petal length greater than the average size.
    > Command:
    > ```sh
    > awk -F "," '{ sum += $3 } END { avg = sum / NR; if ($3 > avg) print }' /home/student/iris.data
    > ```
11. Using `/etc/passwd`, extract the user and home directory fields for all users on your student machine for which the shell is set to `/bin/false`.

   > Command: `awk -F ":" '$7 == "/bin/false" { print $1, $6 }' /etc/passwd`

   Explanation:
   - `awk` is a powerful text processing tool that allows you to process data based on patterns and actions.
   - `-F ":"` sets the field separator as a colon. In `/etc/passwd`, each line consists of multiple fields separated by colons.
   - `$7 == "/bin/false"` is the condition that checks if the seventh field (shell) is set to `/bin/false`.
   - `{ print $1, $6 }` is the action that prints the first field (username) and the sixth field (home directory) if the condition is true.
   - `/etc/passwd` is the input file that contains user information.

   The command uses `awk` to process the `/etc/passwd` file. It sets the field separator as a colon and checks if the shell field is set to `/bin/false` for each line. If the condition is true, it prints the username and home directory fields. This command helps extract specific information about users whose shell is set to `/bin/false`.
