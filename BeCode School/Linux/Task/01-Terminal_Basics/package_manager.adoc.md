
# Package Manager

**Type of challenge:** learning  
**Duration:** 30 min  
**Team challenge:** solo

## Learning objectives

At the end of this challenge, you should be able to:

- Update your computer
- Install packages
- Remove packages
- Search for packages

## Requirements

This drill assumes you know how to:

- Consult the manual within the terminal

## The mission

You need to install Chromium on your machine, and you've been told that most Unix operating systems have a tool for that called the package manager.

You've heard that the package manager for Ubuntu-based distributions is `apt-get`. Open your terminal and read its manual to understand it, then follow the instructions below.

**Note:** If you use another distribution, find out which package manager it uses and research it.

## Instructions

1. Update all the packages on your system using the `apt-get` command.
    
    shellCopy code
    
    `sudo apt-get update`
    
    Explanation: The `apt-get update` command fetches the latest package information from the repositories. This ensures that you have the most up-to-date list of packages available for installation.
    
2. Search if your distribution has Chromium using the `apt-cache` command.
    
    shellCopy code
    
    `apt-cache search chromium`
    
    Explanation: The `apt-cache search` command allows you to search the package cache for a specific package. In this case, you're searching for the Chromium package.
    
3. Install Chromium using the `apt-get` command.
    
    shellCopy code
    
    `sudo apt-get install chromium-browser`
    
    Explanation: The `apt-get install` command installs the specified package, in this case, Chromium. By adding `sudo` before the command, you run it with administrative privileges.
    
4. Launch Chromium by searching for it in your application launcher or running the `chromium-browser` command in the terminal.
    
    shellCopy code
    
    `chromium-browser`
    
    Explanation: After successfully installing Chromium, you can launch it like any other application. You can either search for it in your application launcher or run the `chromium-browser` command in the terminal.
    
5. Remove Chromium using the `apt-get` command.
    
    shellCopy code
    
    `sudo apt-get remove chromium-browser`
    
    Explanation: If you want to remove Chromium from your system, you can use the `apt-get remove` command followed by the package name (`chromium-browser`). This command will uninstall the package, including its associated files and configurations.
    

## Useful info

There are plenty of package managers across various operating systems. For example:

- Mac uses Homebrew (`brew`)
- Arch Linux uses Pacman (`pacman`)
- Node.js uses npm (`npm`)
- Python uses pip (`pip`)
- PHP uses Composer (`composer`)

Package managers are tools designed to simplify the process of installing, updating, and managing software packages and dependencies on a system. They provide a centralized and efficient way to handle software installations, making it easier to maintain a consistent and up-to-date system.

## Resources

- [apt-get tutorial](https://help.ubuntu.com/community/AptGet/Howto)