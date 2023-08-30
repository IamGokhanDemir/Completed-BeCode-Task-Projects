
# Bash Environment

To connect to the virtual machine 10.12.181.X, use the following credentials:
- **IP**: 10.12.181.X
- **User**: student
- **Password**: student

## Environment Variables

Environment variables influence the behavior of software on your system. For example, the "LANG" environment variable determines the language that software uses to communicate with the user.

Variables consist of names assigned to values. For instance, a French user's system may assign the value "fr_FR.UTF-8" to the "LANG" variable.

The meaning and value type of an environment variable are determined by the application using it. Several well-known environment variables have predefined meanings and values, widely used by many applications.

To view environment variables in bash, run the `env` command:

```bash
student@student:~$ env
XDG_SESSION_ID=85
TERM=xterm-256color
SHELL=/bin/bash
...
HOME=/home/student
LANGUAGE=en_US:en
LOGNAME=student
```

Alternatively, you can use the `printenv` command.

You can retrieve the value of a variable by using the "$" sign followed by its name. For example:

```sh
student@student:~$ echo $LANGUAGE
en_US:en
```

### Assigning a Value to a Variable

You can assign a value to a variable using the "=" operator.

Example:
```sh
student@student:~$ MYVAR='MyValue'
```

However, when creating a variable in this way, it is only available to you and not to all sub-processes active in the session. To make a variable accessible to sub-processes, it needs to be exported to the environment.

To export a variable, use the `export` command:

```sh
export MYNAME='Mitnick'
```

You can verify this by creating a variable without exporting it and then echoing the variable:

```sh
student@student:~$ TEST='test'
student@student:~$ echo $TEST
test
```

Now start a new sub-process by running a new bash:

```sh
student@student:~$ bash
```

Echo the `$TEST` variable again:

```sh
student@student:~$ echo $TEST

student@student:~$ 
```

Repeat the operation, but this time export the variable:

```sh
student@student:~$ export TEST="test"
student@student:~$ echo $TEST
test
student@student:~$ bash
student@student:~$ echo $TEST
test
```

### Export or Not?

Exporting variables is necessary when you want to make them available for subsequent commands or processes, typically to share the environment with a child process. Use environment variables (with export) for the following purposes:

- Setting up the environment of a child process or shell
- Setting a variable that a bash script running from the parent shell would use
- Setting environment variables for terminal multiplexers such as screen or tmux
- Establishing the build environment for build scripts and tools

Shell variables (without export) are used when you want variables to be available only in the parent shell and avoid polluting the child process environment. They are typically used for:

- Loop counter variables
- Temporary variables

### Exercises

1. On your student machine what is the value of the FLAG environment variable?
> Command: `echo $FLAG`
> Explanation: The command `echo` is used to print the value of the `FLAG` environment variable. The `$` symbol is used to reference the value of a variable. By typing `echo $FLAG`, the value of the `FLAG` environment variable will be displayed.
> Flag: `BC{EXPORT_B4SH_FLAG}`

2. Currently, if you notice your machine, the variable you have created will be deleted. What should you do to make your variable persistent? (With a Bash shell).
> Commands:
> - Open the appropriate shell configuration file. In this case, it would be `~/.bashrc`.
> - Add the command to set the environment variable in the file. For example: `export FLAG="your_value"`
> - Save the file and exit.
> - Reload the shell configuration by running the command `source ~/.bashrc`.
> Explanation: To make an environment variable persistent, you need to add the appropriate command to set the variable in the shell configuration file. In this case, the command `export FLAG="your_value"` should be added to the `~/.bashrc` file. After saving the file and reloading the shell configuration, the variable will be set every time the shell starts.

## History

In the terminal, have you ever tapped on the up or down arrows to return to a command you had previously used?

![history](https://www.commitstrip.com/wp-content/uploads/2017/02/Strip-La-flemme-de-retaper-650-finalenglsih-1.gif)

Well, this is made possible by a file humbly named 'History'. This is located in your user file /home/user/. In the virtual machine, it is the file `/home/student/.bash_history`.

```sh
student@student:~$ ls -la
total 144
drwxr-xr-x 5 student student  4096 May  3 22:43 .
drwxr-xr-x 4 root    root     4096 May  1 17:39 ..
-rw------- 1 student student   863 May  2 08:30 .bash_history
-rw-r--r-- 1 student student   220 May  1 17:39 .bash_logout
-rw-r--r-- 1 student student  4003 May  3 22:43 .bashrc
drwx------ 2 student student  4096 May  1 17:40 .cache
-rw-r--r-- 1 root    root      209 May  1 23:12 employee.txt
drwxrwxr-x 2 student student  4096 May  1 21:25 findme
```

As you can see, the `.` in front of the file indicates that it is a hidden file.

> ⚠️ Depending on the shell used, the file name may change. You will often find it under `.history`

```sh
student@student:~$ cat .bash_history 
sudo -l
dh
ls
cd /var
ls
cd /www
cd www
ls
cd html
ls
```

If we inspect the file, we can see all the history of our previously typed commands. There is also a command that displays the same thing: `history`.

```sh
student@student:~$ history
    1  sudo -l
    2  dh
    3  ls
    4  cd /var
    5  ls
    6  cd /www
    7  cd www
    8  ls


```

When it is executed, `history` returns all the commands and their entry number (first column). We can use this number to re-run commands without having to type them again. For example, if you want to re-execute command number 42, you just have to enter:

```
student@student:~$ !42
```

The keyboard shortcut Ctrl+R allows you to enter the search mode in the history. The prompt looks like this:

```sh
(reverse-i-search):
```

You just have to enter the first characters of the command you want to search for so that the prompt offers you the most recent commands corresponding to your keystrokes, then press Enter when you have found the right command.

> ⚠️ While this file can be useful for us users, it is also useful for hackers. Sometimes the history can contain important information such as credentials that could help them escalate privileges.
>
> ⚠️ Also, when a machine has been compromised, it can be interesting for the analyst to check if the hacker has left some traces in the history.

### Exercises:

1. **From a hacker's perspective**, look for information that might be useful to you in the `.history` file.
> Command: `cat .bash_history`
> Explanation: The command `cat` is used to display the contents of a file. By running `cat .bash_history`, the contents of the `.bash_history` file will be displayed, which includes the command history of the user. From a hacker's perspective, this can provide information that might be useful for further exploitation or privilege escalation.

2. **From an analyst's perspective**, look for information that might be useful to you in the `.history` file.
> Command: `cat .bash_history`
> Explanation: The command `cat` is used to display the contents of a file. By running `cat .bash_history`, the contents of the `.bash_history` file will be displayed. From an analyst's perspective, this file can be useful for investigating and understanding the actions performed by a user on the system, identifying any suspicious or malicious commands that were executed, or tracing the steps of an incident.

## Custom Aliases

Linux users often find themselves using the same commands repeatedly. Instead of typing or copying the same command over and over, you can create aliases to save time and increase productivity. Aliases are custom shortcuts that represent a command or a set of commands, with or without custom options. You might already be using aliases on your Linux system.

To view the list of defined aliases in your profile, you can simply execute the `alias` command.

```sh
student@student:~$ alias
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l='ls -CF'
alias la='ls -A'
alias ll='ls -alF'
alias ls='ls --color=auto'
```

The output shows the default aliases defined for the user in Ubuntu 16. For example, the alias `ll` represents the command `ls -alF`. When you run `ll`, it is equivalent to running `ls -alF`.

To create an alias, you can use a single character that will be equivalent to a command of your choice.

### How to Create Aliases in Linux

Creating aliases in Linux is a relatively easy and quick process. There are two types of aliases: temporary and permanent. Let's explore both types.

* **Creating Temporary Aliases**: To create a temporary alias, use the `alias` command followed by the name you want to use for executing the command, an equals sign (=), and the command you want to alias enclosed in quotes.

  ```sh
  $ alias shortName="your custom command here"
  ```

* **Creating Permanent Aliases**: To keep aliases between sessions, you can save them in your user's shell configuration profile file. The file location depends on the shell you're using:
    - Bash: `~/.bashrc`
    - ZSH: `~/.zshrc`
    - Fish: `~/.config/fish/config.fish`

  The syntax for creating a permanent alias is almost the same as creating a temporary alias. The only difference is that you'll be saving it in a file this time. For example, in Bash, you can open the `.bashrc` file with your favorite text editor:

  ```sh
  nano ~/.bashrc
  ```

  Find a suitable place in the file to add your aliases. For organization purposes, you can leave a comment before your aliases, like this:

  ```sh
  # My custom aliases
  alias home="ssh -i ~/.ssh/mykep.pem tecmint@192.168.0.100"
  alias ll="ls -alF"
  ```

  Save the file. The changes will be automatically loaded in your next session. If you want to use the newly defined alias in the current session, run the following command:

  ```sh
  source ~/.bashrc
  ```

Now you can optimize your workspace and create your own aliases to enhance your productivity.