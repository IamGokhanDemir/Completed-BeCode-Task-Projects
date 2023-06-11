
# Discover the Terminal

Time to discover the terminal and work with the most common commands.

## Goals

You should be able to use the right terminal syntax:

- Move around the file system
- Show the contents of a folder
- Create a folder
- Create a file
- Change a filename
- Remove a file

As you'll see, the exercises below give you the objective, but not how to do them. When you don't know, it's time to ask your new BFF: Google! That's one core rule at BeCode: before asking your neighbor for help, ask the internet!

## Deadline

ETA: 3 hours

## The Drill

**All the exercises that follow can only be executed through the terminal!**

To practice, open a Terminal window and follow the instructions below:

1. **Go to your desktop folder**: 
```
cd ~/Desktop
```
This command navigates to your desktop folder.

2. **Check the current directory**: 
```
pwd
```
This command prints the current directory name.

3. **Create a file `text.txt`**: 
```
touch text.txt
```
This command creates a new empty file named `text.txt`.

4. **Open the file and write a line of text**: 
```
nano text.txt
```
This command opens the file `text.txt` in a terminal-based text editor called `nano`. You can write a line of text, save the file, and exit the editor.

5. **Make a folder called `Octocat`**: 
```
mkdir Octocat
```
This command creates a new folder named `Octocat`.

6. **Go to the `Octocat` folder**: 
```
cd Octocat
```
This command navigates to the `Octocat` folder.

7. **Create the file `yolo.md`**: 
```
touch yolo.md
```
This command creates a new empty file named `yolo.md` inside the `Octocat` folder.

8. **Open the file and enter your name**: 
```
nano yolo.md
```
This command opens the file `yolo.md` in the `nano` editor. You can enter your name, save the file, and exit the editor.

9. **Create the file `readme.md`**: 
```
touch readme.md
```
This command creates a new empty file named `readme.md` inside the `Octocat` folder.

10. **Write a paragraph about your projects**: 
```
nano readme.md
```
This command opens the file `readme.md` in the `nano` editor. You can write a paragraph about the projects you want to achieve during your training, save the file, and exit the editor.

11. **Create a file with your name**: 
```
touch <your_first_name>_<your_last_name>.md
```
Replace `<your_first_name>` and `<your_last_name>` with your actual first name and last name. This command creates a new empty file named after your first and last name with the `.md` extension inside the `Octocat` folder.

12. **Write a text about why you want to be a BeCode Developer**: 
```
nano <your_first_name>_<your_last_name>.md
```
Replace `<your_first_name>` and `<your_last_name>` with your actual first name and last name. This command opens the file named after your first and last name in the `nano` editor. You can write a text explaining why you want to be a BeCode Developer, save the file, and exit the editor.

13. **Remove the file `text.txt`**:

 
```
rm text.txt
```
This command removes the file named `text.txt`.

14. **List the contents of the `Octocat` directory**: 
```
ls Octocat
```
This command lists the contents of the `Octocat` directory, showing the files and folders inside it.

15. **Create the folder `Skills` and a file `successful.md`**: 
```
mkdir Skills
touch Skills/successful.md
```
These commands create a new folder named `Skills` and a new file named `successful.md` inside the `Skills` folder.

16. **Write down your computer skills**: 
```
nano Skills/successful.md
```
This command opens the file `successful.md` in the `nano` editor. You can write down your computer skills (languages you know or want to know), save the file, and exit the editor.

17. **Create the folder `becode_projects`**: 
```
mkdir becode_projects
```
This command creates a new folder named `becode_projects`.

18. **Press `CTRL+R` and see what happens**: 
```
CTRL+R
```
Pressing `CTRL+R` activates the reverse search functionality in the terminal, allowing you to search and execute previous commands by typing keywords.

19. **Use reverse search with `CTRL+R`**: 
```
CTRL+R
```
Pressing `CTRL+R` again and typing keywords from your last command will allow the terminal to find and display that command. Press Enter to execute it.

Once you have completed these steps, you will have practiced various commands for navigating the file system, creating files and folders, editing files, and using some useful shortcuts. Keep exploring and experimenting with the terminal to become more comfortable and proficient with its commands.
