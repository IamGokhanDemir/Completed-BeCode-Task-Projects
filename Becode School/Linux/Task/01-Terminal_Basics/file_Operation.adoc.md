## File Operation

- Type of challenge: learning
- Duration: 60 min
- Team challenge: solo

### Learning Objectives

By the end of this challenge, you should be able to:

- Read a file
- Create a file
- Create a folder
- Move a file
- Copy a file
- Rename a file
- Delete a file
- Delete a folder

### Requirements

This briefing assumes that you know how to:

- Consult the manual within the terminal

### The Mission

You've heard of a bunch of new commands to work with files: `cat`, `touch`, `mkdir`, `mv`, `cp`, `rm`, and `rmdir`. Open your terminal and read their manuals to understand them, then follow the instructions below.

### Instructions

1. Create a file named `one.txt`:
    
    bashCopy code
    
    `touch one.txt`
    
2. Type the following command to add the text "Hello World" to the `one.txt` file:
    
    bashCopy code: echo creates the text and > will say where it must go
    
    `echo "Hello World" > one.txt`
    
3. Print the content of that file on the screen:
    
    bashCopy code
    
    `cat one.txt`
    
4. Create a folder named `story`:
    
    arduinoCopy code: This creates a directory
    
    `mkdir story`
    
5. Move `one.txt` into that folder:
    
    bashCopy code
    
    `mv one.txt story/`
    
6. Copy `one.txt` inside the `story` folder as `two.txt`:
    
    bashCopy code
    
    `cp story/one.txt story/two.txt`
    
7. Print the content of both files:
    
    bashCopy code
    
    `cat story/one.txt cat story/two.txt`
    
8. Rename `one.txt` to `part_one.txt` and `two.txt` to `part_two.txt`:
    
    bashCopy code
    
    `mv story/one.txt story/part_one.txt mv story/two.txt story/part_two.txt`
    
9. Type the following command to add the text "I am a junior at BeCode." to the `story/part_two.txt` file:
    
    bashCopy code: echo creates the text and > will say where it must go
    
    `echo "I am a junior at BeCode." > story/part_two.txt`
    
10. Print the content of both files simultaneously:
    
    bashCopy code
    
    `cat story/part_one.txt story/part_two.txt`
    
11. Remove the folder `story` and all its content:
    
    - Option 1: Use `rm` command with the `-r` flag to remove the folder recursively:
        
        bashCopy code: This will remove the folder/directory with content inside
        
        `rm -r story`
        
    - Option 2: Use `rmdir` command to remove the empty folder:
        
        arduinoCopy code: This command can only be used when the file/directory is empty
        
        `rmdir story`
        

Remember to consult the [[Basic Linux command for command prompt]] for each command if you need further information. Enjoy the challenge!