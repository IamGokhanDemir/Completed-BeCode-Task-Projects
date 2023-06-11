
# Navigation

**Type of challenge:** learning  
**Duration:** 30 min  
**Team challenge:** solo

## Learning objectives

At the end of this challenge, you should be able to:

- Move around the file system
- List the content of a directory
- Get your position on the file system

## Requirements

This briefing assumes that you know how to:

- Consult the manual within the terminal

## The mission

You've heard of three new commands to explore the file system: `cd`, `ls`, and `pwd`. Open your terminal and read their manuals to understand them, then follow the instructions below.

## Instructions

1. Print your location on the screen using the `pwd` command.

   ```shell
   pwd
   ```

   Explanation: `pwd` stands for "print working directory." It displays the current working directory, which is your current location within the file system.

2. Print the content of your current directory using the `ls` command.

   ```shell
   ls
   ```

   Explanation: `ls` lists the files and directories in the current directory. It helps you view the contents of the directory you're currently in.

3. Print the content of the root directory (`/`) using the `ls` command.

   ```shell
   ls /
   ```

   Explanation: By specifying `/` as the argument to `ls`, you list the files and directories in the root directory, which is the top-level directory in the file system.

4. Move to the folder `/bin` using the `cd` command.

   ```shell
   cd /bin
   ```

   Explanation: `cd` is short for "change directory." It allows you to navigate to a different directory. In this case, you're moving to the `/bin` directory, which contains essential executable files.

5. Print your new location using the `pwd` command.

   ```shell
   pwd
   ```

   Explanation: After changing directories, you can verify your new location by using the `pwd` command again.

6. Go back to your home folder using the `cd` command.

   ```shell
   cd
   ```

   Explanation: By using `cd` without any arguments, you return to your home folder, which is the default directory when you open the terminal.

7. Print your current location again using the `pwd` command to confirm that you're back in the home folder.

   ```shell
   pwd
   ```

   Explanation: By running `pwd` once more, you can confirm that your current location is indeed your home folder.

## Optional

Ever wished you could teleport? Well, check out `pushd` and `popd` to get amazing warping power.

- Use the `pushd` command followed by a directory path to move to any location on your file system for a quick job. This command also saves your current location.

  ```shell
  pushd /path/to/directory
  ```

  Explanation: `pushd` allows you to change to a different directory and saves your current location in a directory stack. It enables you to easily switch between directories without losing track of your previous location.

- Use the `popd` command to go back to the previously saved location after you're done with the quick job. This allows you to easily switch between different directories without manually navigating each time.

  ```shell
  popd
  ```

  Explanation: `popd` pops the top directory from the directory stack and changes your current directory back to the previous location you saved with `pushd`. This makes it convenient to return to a previously visited directory without the need to navigate manually.