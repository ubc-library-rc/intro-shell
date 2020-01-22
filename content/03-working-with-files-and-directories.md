---
 layout: default
 title: Working with files and directories
 parent: Outline
 nav_order: 3
---

# Working with files and directories

Now that you know how to move around in the system we can try making changes to it.

First, let's navigate to our working folder.

Input
{: .label .label-green}
~~~
$ cd Desktop
$ cd shell-lesson
$ pwd
~~~
Output
{: .label .label-yellow}
~~~
~~~
Note that you can jump directly to a directory you already know is there by just entering the full path.
~~~
$ cd Desktop/shell-lesson
~~~
And you can use "tab" to autocomplete commands quickly.

From this point on we will be working in this folder.

## Creating a directory
Let's try creating a directory and moving in and out of it.
Input
{: .label .label-green}
~~~
$ mkdir mydirectory
$ cd mydirectory
$ ls
~~~
Output
{: .label .label-yellow}
~~~
~~~

You can see there is now a new directory in the same location. If we try going into it we will see that it's empty.

There is also a handy way to see this change visually.
~~~
$ open .
~~~

# Creating a file
Now let's create a file. There are built-in text editors accessible through the shell. Nano is a commonly used editor.

Input
{: .label .label-green}
~~~
$ touch myfile
$ nano myfile
$ ls
~~~
Output
{: .label .label-yellow}
~~~
~~~

## Reading files

Sometimes you want to get a more in-depth sense of what is in the files in a directory.

We've already talked a bit about looking at the information about the file.

Input
{: .label .label-green}
~~~
$ ls -lh
~~~

But you can also quickly open the entirety of the file from the command line.

Input
{: .label .label-green}
~~~
$ cat
~~~

If at any point in looking through information you want to jump back to the command line just enter CTRL+C, the C stands for command line in this.

The command "cat" gives you everything in a file all at once which is great when working with smaller files but can be overwhelming with larger files. Sometimes all you want to see is a small subset of a file.

Another option similar to "cat" is "less" which similar to the manual shows you only what fits in your terminal window and then lets you move through the content by hitting enter.

Input
{: .label .label-green}
~~~
$ less
~~~

The command "head" defaults to showing the first ten lines in a file.

Input
{: .label .label-green}
~~~
$ head
~~~

You can ask head to show more or less as needed.

"Tail" works similarly

Input
{: .label .label-green}
~~~
$ tail
~~~

Up arrow in a black command to reuse commands.

You can use this method to quickly view all of a type of file in a directory.

Input
{: .label .label-green}
~~~
$ head *.txt
~~~

## Moving, copying, and deleting files and directories

Input
{: .label .label-green}
~~~
$ head mv
$ ls
~~~

You can copy files, for example if you want to create a backup.

Input
{: .label .label-green}
~~~
$ cp file backup_file
~~~

And you can delete files through the "rm" command which stands for remove.

Input
{: .label .label-green}
~~~
$ rm backup_file
~~~

You can also delete directories but that requires an additional (and dangerous) flag. -r stands for "recursive" which essentially tells the command "rm" to keep going through all of the files that are inside the directory as well until there's nothing left.

Input
{: .label .label-green}
~~~
$ rm -r myfirstfolder
~~~
