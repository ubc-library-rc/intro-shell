---
 layout: default
 title: Navigating the file system
 parent: Outline
 nav_order: 2
---
# Navigating the file system

Let's start by opening the unix shell. There are a few things you are likely to see right away. A cursor that is flashing next to a $ indicates where the command line begins. If you see the dollar sign it means that the command line is ready to take commands.
*Input*
```console
$
```
You are communicating with your computer by giving it commands and having it react to those commands.

Let's enter our first command "pwd" which stands for "print working directory" and will tell us where we are in the system. The term "directory" refers to what you might visually think of as a "folder" when browsing your file system.

Input {: .label .label-green}
```console
$ pwd
```

```console
$ ls
```

```console
$ ls -l
```

```console
$ ls -lh
```

Getting help
```console
$ man ls
```
or
```console
$ ls --help
```

You can only go to places that exist.
*Input*
```console
$ cd Desktop
```
*Output*

The case of the directory doesn't matter on Mac or PC but does on Linux.

Switch back and forth between two directories.

```console
$ cd -
```
Viewing things graphically.
```console
$ open .
```
