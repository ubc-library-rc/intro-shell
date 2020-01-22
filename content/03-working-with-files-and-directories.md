---
 layout: default
 title: Working with files and directories
 nav_order: 3
---

# Working with files and directories

```console
$ cd
$ cd Desktop/intro-shell
$ pwd
```

Let's try creating a directory and moving in and out of it.
```console
$ mkdir mydirectory
$ cd mydirectory
$ pwd
```
You can see what is happening visually.
```console
$ open .
```
Use "tab" to autocomplete commands quickly.

Now let's create a file. There are built-in text editors accessible through the shell. Nano is a commonly used editor.

```console
$ touch myfile
$ nano myfile
$ ls
```
Reading files.

```console
$ ls -lh
```
To quickly open the entirety of a file:
```console
$ cat
```
Escaping from something huge like this is easy, just use CTRL+X and CTRL+C to return to the command line.

A simpler way to do this is to use less which essentially paginates.


To look at the head
```console
$ head
```

```console
$ tail
```

```console
$ less
```

Up arrow in a black command to reuse commands.

Wildcards

```console
$ head *.txt
```

Moving, copying, and deleting files and directories

```console
$ mv
```

```console
$ ls
```
