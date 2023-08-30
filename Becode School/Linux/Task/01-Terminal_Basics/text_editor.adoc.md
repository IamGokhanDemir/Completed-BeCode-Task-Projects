
# Text Editor

Type of challenge: **learning**  
Duration: **60 min**  
Team challenge: **solo**

## Learning objectives

At the end of this challenge, you should be able to:

- Make quick edits with `nano`
- Make quick edits with `vim`

## Requirements

This briefing assumes that:

- `nano` is installed on your machine
- `vim` is installed on your machine
- You know how to remove a file

## The mission

You have to create a file `text.txt` containing the text below on your system using a terminal text editor.

```
I need to be created.
Just because!
```

To do so, you can use either `nano` or `vim`. Follow the instructions below.

### Instructions

1. **Research about the text editor `nano`:** Take some time to learn about the `nano` text editor. You can search for tutorials or guides online to understand its features and commands.

2. **Create the file `text.txt` with `nano`:** Open a terminal window and run the following command:
   ```
   nano text.txt
   ```
   This will open the `nano` editor with a blank file named `text.txt`. Type or paste the given text into the editor. Press `Ctrl + O` to save the file, and then press `Ctrl + X` to exit `nano`.

3. **Remove `text.txt`:** If you want to remove the `text.txt` file, use the following command:
   ```
   rm text.txt
   ```
   This will permanently delete the file from your system.

4. **Type `vimtutor` and read through the tutorial:** In the terminal, type the command:
   ```
   vimtutor
   ```
   This will launch a tutorial that provides a hands-on learning experience with the `vim` text editor. Follow the instructions and complete the tutorial to improve your `vim` skills.

5. **Create the file `text.txt` with `vim`:** Open a terminal window and run the following command:
   ```
   vim text.txt
   ```
   This will open the `vim` editor with a blank file named `text.txt`. Press `i` to enter the insert mode, and then type or paste the given text into the editor. Press `Esc` to exit insert mode, and then type `:wq` to save the file and exit `vim`.

### Explanation

The mission introduces two popular terminal text editors: `nano` and `vim`. By researching `nano` and `vim` before starting the tasks, you can gain familiarity with their features and usage.

First, you create the `text.txt` file using `nano`, a beginner-friendly text editor. This allows you to quickly make edits and save the file.

Next, you remove the `text.txt` file using the `rm` command to demonstrate file deletion.

To enhance your text editing skills further, you explore the `vimtutor` tutorial, which guides you through the usage of the `vim` editor. This tutorial provides a hands-on learning experience and helps you understand the powerful features of `vim`.

Finally, you create the `text.txt` file again, but this time using `vim`. `vim` is a highly customizable and powerful text editor, widely used by advanced users.

### Resources

- [Vim adventure](https://vim-adventures.com/)

## Congrats

You can now be a writer from within the command line. Go forth and write away!

![Congratulations](https://media.giphy.com/media/iFU36VwXUd2O43gdcr/giphy.gif)