---
layout: default
title: Resources
nav_order: 49
---

# Cheatsheets

* [Library Carpentry's UNIX shell reference.](https://librarycarpentry.org/lc-shell/reference.html)
* [Software Carpentry's more detailed shell reference.](https://swcarpentry.github.io/shell-novice/reference/)
* [Command line cheat sheet from Tower](https://www.git-tower.com/blog/command-line-cheat-sheet/)

## Basic commands

This is a quick summary of the commands mentioned in this workshop by section.

### Navigating the file system

| pwd | print working directory to find out where in the system you are |
| ls  | view list of a file or directory |     
| ls -l  | view more detailed list of files or directory  |  
| ls -lh | view more detailed list and make numbers more human-readable  |   
| cd | navigate between directories |
| cd .. | go back one step while navigating between folders |
| cd - | jump back to previous directory however many steps ago it was |
| man | open a manual about a command |

### Working with files and directories

| mkdir | create a directory |
| touch | create a file |
| nano | edit a text file through an editor within the shell |
| mv | move a file to a different location or rename it which is a form of moving |
| cp | copy a file or directory |
| rm | remove a file or empty directory |
| rm -r | remove recursively directory and all files and other directories in it |
| cat  | view contents of a file |
| less | view contents but paginated (use q to quit) |
| head | view the first ten lines of a file by default |
| head -n15 | view the first 15 lines (or any other number indicated by the -n flag) |
| tail | view the last ten lines of a file. Similar to head, the -n flag allows you to view more or less |

### Automating with loops

| echo | print string that is being passed as an argument to let us know what the status of the script is |
