---
 layout: default
 title: Working with files and directories
 parent: Outline
 nav_order: 3
---

# Working with files and directories

Now that you know how to move around in the system we can try making changes to it.

First, let's navigate to our Desktop.

Input
{: .label .label-green}
~~~
$ cd Desktop
$ pwd
~~~
Output
{: .label .label-yellow}
~~~
/Users/egrguric/desktop
~~~

If the directory name or filename is too long to type, you can type the first few letters to differentiate the address and use "tab" button to autocomplete directory and file names quickly.

## Creating a directory

Let's try creating a directory and moving into it.

Input
{: .label .label-green}
~~~
$ mkdir myfirstdirectory
$ ls
~~~

You can see there is now a new directory in the same location. If we try going into it we will see that it's empty.

There is also a handy way to see this change visually.
~~~
$ open .
~~~

Output
{: .label .label-yellow}

![Finder window with empty directory](myfirstdir.png)

## Creating a file

Now let's create a file. There are built-in text editors accessible through the shell. These editors are handy if you need to make a quick change from the shell or want to avoid having to open another program while you are working in the terminal. **Nano** is a commonly used text editor.

Input
{: .label .label-green}
~~~
$ touch myfile.txt
$ nano myfile.txt
$ ls
~~~
Output
{: .label .label-yellow}
~~~
myfile
myfirstdirectory
~~~

Please note that when working with the command line interpreter, spaces in file and directory names can be misinterpreted as separators between arguments. To avoid any confusion or errors, it is recommended to refrain from using spaces in file and directory names. Instead, consider using periods (`.`), dashes (`-`), or underscores (`_`) as alternatives. If you come across situations where you need to reference file or directory names that contain spaces or special characters, it is advisable to enclose the name within quotation marks (`""`). This ensures that the interpreter correctly recognizes the entire name as a single entity. Following these practices will help prevent any unexpected behavior or issues when working with files and directories through the command line.

Note: `nano` is a simple text editor commonly found in the Terminal. While it may not be as powerful and flexible as other text editors, it serves as a convenient option for basic editing tasks. `nano` is pre-installed on Unix shells, and this makes it particularly useful for editing text files on remote machines. If you're interested in exploring different text editors and expanding your knowledge, check out the [Introduction to Development Environment](https://ubc-library-rc.github.io/intro-development-environment/content/02.Editors.html) workshop.

When naming files, it is customary to follow the convention of `filename.extension`, where the `extension` denotes the file type. For instance, a `.txt` extension indicates a plain text file, while a `.png` extension signifies a PNG image file, and so on. Each file type has its own specific encoding, and it should be opened using an application capable of decoding that particular format. By using the correct file extension, the operating system recognizes the file type and attempts to open it with the appropriate application. This ensures that the file is processed correctly, utilizing the intended software for viewing, editing, or executing its contents.

## Moving, copying, and deleting files and directories

Now let's try moving our new file into our new directory to organize things a bit.

Input
{: .label .label-green}
~~~
$ mv myfile.txt myfirstdirectory/myfile.txt
$ cd myfirstdirectory
$ ls
~~~
Output
{: .label .label-yellow}
~~~
myfile.txt
~~~

The first argument contains the file we are moving and the second one is where it is to go. To rename a file, you can use the new name as the destination in a `mv` command. 

Input
{: .label .label-green}
~~~
$ mv myfile.txt mynewfile.txt
$ ls
~~~
Output
{: .label .label-yellow}
~~~
mynewfile.txt
~~~

Note: Be careful when specifying the file name. `mv` silently overwrites any existing files with the same name and could cause data loss. With the `-i` option, you can set `mv` to ask for confirmation before writing. 

The "cp" command lets you copy files, for example, if you want to create a backup, and it works very much like `mv`. 

Input
{: .label .label-green}
~~~
$ cp mynewfile.txt backup_mynewfile.txt
~~~

You can use the `-r` option to copy a directory and all its contents. `-r` specifies the recursive copying.

And you can delete files through the "rm" command which stands for remove.

Input
{: .label .label-green}
~~~
$ rm backup_mynewfile.txt
ls
~~~
Output
{: .label .label-yellow}
~~~
mynewfile.txt
~~~

You can also delete directories but that requires an additional (and dangerous) flag. `-r` stands for "recursive" which essentially tells the command "rm" to keep going through all of the files that are inside the directory as well until there's nothing left. Be careful when using this option, as the Unix shell does not have a trash bin and deleted files are unlinked from the file system. Tools for finding and recovering deleted files exist, but there's no guarantee they will work in any particular situation. 

Note: with `-i` option, the shell prompt before removal and we have a chance to checkl that we are deleting only the files we want to remove.

Input
{: .label .label-green}
~~~
$ cd ..
$ ls
$ rm -r myfirstdirectory
$ ls
~~~
Output
{: .label .label-yellow}
~~~

~~~

### Using wildcards

`*` is a wildcard, which matches zero or more characters. When the shell sees a wildcard, it expands the wildcard and creates a list of matching files names before running the command. For example, if you want to copy all the PDF files in a directory, you can run the following command:

Input
{: .label .label-green}
~~~
$ cp firstdirectory/*.pdf seconddirectory/
~~~ 

## Reading files

Let's make a few files to work with for the next activity.

Sometimes you want to get a more in-depth sense of what is in the files in a directory.

We've already talked a bit about looking at the information about the files.

Input
{: .label .label-green}
~~~
$ touch file1.txt file2.txt file3.txt file4.txt
~~~
Output
{: .label .label-yellow}
~~~
file1.txt
file2.txt
file3.txt
file4.txt
~~~

Input
{: .label .label-green}
~~~
$ ls -lh
~~~

But you can also quickly open the entirety of the file from the command line. The `cat` command gets its name from 'concatenate' and prints the contents of files on the screen.

Input
{: .label .label-green}
~~~
$ cat file1.txt
~~~

Output
{: .label .label-yellow}
~~~

~~~

Input
{: .label .label-green}
~~~
$ nano file1.txt
~~~

Output
{: .label .label-yellow}
~~~
My super secret plan.

Part 1

Part 2

Part 3

Part 4

Part 5
~~~

If the file is large, you might want to get only the first few lines. We can run another command called `head` for that. Using `-n 5` option with `head` tells it to print only the first 5 lines of the file. The command `head` defaults to showing the first ten lines in a file.

Input
{: .label .label-green}
~~~
$ head file1.txt
~~~

Output
{: .label .label-yellow}
~~~
My super secret plan.

Step 1

Step 2

Step 3

Step 4

~~~

You can use this method to quickly view all files of a certain type in a directory.

Input
{: .label .label-green}
~~~
$ head *.txt
~~~

Or only the first line of all of the files which might be useful if there are a lot of them. 

Input
{: .label .label-green}
~~~
$ head -n1 *.txt
~~~

`tail` works similarly and prints the end of your files.

Input
{: .label .label-green}
~~~
$ tail file1.txt
~~~

Output
{: .label .label-yellow}
~~~

Step 3

Step 4

Step 5

Step 6

World domination!
~~~

`less` can be used to read the content of a file **one screen** at a time. 

Input
{: .label .label-green}
~~~
$ less file1.txt
~~~

Output
{: .label .label-yellow}
~~~
My super secret plan.

Step 1

Step 2

Step 3

Step 4

Step 5
:
~~~

Use the enter key to move through the file and `q` to "quit" or exit the file.

## Finding things

`grep` is the name of a very useful command-line program that searches within files for a particular pattern. For example, to find lines that contain the number `3` in our file, we run:

Input
{: .label .label-green}
~~~
$ grep 3 file1.txt
~~~
Output
{: .label .label-yellow}
~~~
Step 3
~~~

To search for a phrase, we should put the phrase in quotes. 

While `grep` finds lines in files, the `find` command finds files within directories. 

Input
{: .label .label-green}
~~~
$ find .
~~~

As `.` means the current working directory, `find`'s output is the names of all the files and directories under the current working directory. With `-name` option, we can specify conditions on the names of the files or directories:

Input
{: .label .label-green}
~~~
$ find . -name *.txt
~~~


