---
 layout: default
 title: Pipelines and automating workflows
 parent: Outline
 nav_order: 3.5
---

# Pipelines and automating workflows

## Pipelines

Arguably, the shell's most powerful feature is pipelines, which let us combine existing programs in new ways. For example, we can ask the shell to capture the output of a command in a file.

Input
{: .label .label-green}
~~~
$ ls -l > list.txt
~~~
{: .shell-input}

The greater than symbol, `>`, tells the shell to redirect the command's output to a file instead of printing it to the screen (the default output). The shell will create the file if it does not exist or will silently overwrite the file.

To pass the output of one command to another command, we can use pipelines. The vertical bar, `|`, between the two commands is called a **pipe** and tells the shell that we want to use the output of the command on the left as the input to the command on the right.

You can also use `grep` to search the history of commands that were run in the shell. To get a list of past commands:

Input
{: .label .label-green}
~~~
$ history
~~~
{: .shell-input}

Now, we use pipelines to send the output of `history` to a `grep` command:

Input
{: .label .label-green}
~~~
$ history | grep cd
~~~
{: .shell-input}

## Variables in the shell

Like scripting languages, the shell lets you define variables and store parameters and values in them. The name of a variable can contain only letters, numbers, or the underscore character. By convention, Unix shell variables have names in UPPERCASE.

You can assign values to variables using the `=` sign.

Input
{: .label .label-green}
~~~
$ NAME="shayan"
~~~
{: .shell-input}

To retrieve the value stored in a variable, simply precede the variable name with the dollar sign (`$`). In certain cases, when establishing connections to remote machines to execute tasks or processes, you may find it necessary to store directory names or file names in variables. This enables easier reference and manipulation of these values within your scripts or commands. To print the value of a variable in a shell script, you can use the `echo` command followed by the variable name preceded by a dollar sign (`$`).

Input
{: .label .label-green}
~~~
$ echo $name
~~~
{: .shell-input}

## Automating with loops

Loops are used to repeat a command or set of commands for each item in a list. Similar to wildcards, using loops can save a lot of time and reduce the amount of typing required.

The structure of a loop is:

~~~
for thing in list_of_things
do
  operation_using $thing # Indentation is not required but helps legibility.
done
~~~

For example, if you want to copy all of the files with the `.doc` extension and add `backup_` to the beginning of their names, you can use the following loop:

~~~
for filename in *.doc
do
  echo "$filename"
  cp "$filename" "backup_$filename"
done
~~~

Notice that as you write a loop in the shell, the indicator changes from `$` to `>`, which essentially means "waiting for the command to finish". A `;` can be used to separate commands written on a single line.

In this example, we are saying that every time a filename has the `.doc` extension, we want to take the name of the file and then make a copy of it while prefixing the file with `backup_`. The result is a backup of every file with a `.doc` extension in our directory.

Let's say we make four files called `one.doc`, `two.doc`, `three.doc`, and `four.doc`.

Input
{: .label .label-green}
~~~
$ touch one.doc two.doc three.doc four.doc
~~~
{: .shell-input}

Output
{: .label .label-yellow}
~~~
one.doc
two.doc
three.doc
four.doc
~~~

Let's run our loop and see what happens. Note that we are telling the script to "echo" the filenames that are getting acted on. This is a way to check that the script is okay and to confirm which files we are affecting.

Input
{: .label .label-green}
~~~
$ for filename in *.doc
> do
>   echo "$filename"
>   cp "$filename" backup_"$filename"
> done
~~~
{: .shell-input}

Output
{: .label .label-yellow}
~~~
four.doc
one.doc
three.doc
two.doc
~~~

If we now run `ls` in the working folder, we see the four backup files.

Output
{: .label .label-yellow}
~~~
one.doc
two.doc
three.doc
four.doc
backup_one.doc
backup_two.doc
backup_three.doc
backup_four.doc
~~~

## Shell Scripts

We can take the commands we repeat frequently and save them in a file to rerun the operations again and again by running a single command. Shell scripts also make it possible to reproduce the same results simply by running your script rather than finding or remembering a long list of commands.

A shell script should have a `.sh` extension, but it is nothing more than a program stored in a text file. You can use `nano` to write a shell script.

Input
{: .label .label-green}
~~~
$ nano script.sh
~~~
{: .shell-input}

To execute the commands in a shell script, we ask the shell to read and run the commands:

Input
{: .label .label-green}
~~~
$ bash script.sh
~~~
{: .shell-input}

## Downloading and archiving

The `tar` command archives multiple files into a TAR file, a common Linux format similar to ZIP. The basic syntax looks like this:

Input
{: .label .label-green}
~~~
$ tar [options] [archive_file] [file or directory to be archived]
~~~
{: .shell-input}

For example, to create a new TAR archive named `newarchive.tar` in the `/home/user/Documents` directory:

Input
{: .label .label-green}
~~~
$ tar -cvf newarchive.tar /home/user/Documents/myfirstdirectory
~~~
{: .shell-input}

In the command above, `c` tells `tar` to create a new archive, `v` sets the screen output to verbose so it will show the result on the screen, and
`f` points to the filename given to the archive. You can also extract a tar archive by passing `-x` or list the contents of an archive by passing `-t`.

To download content and files from web servers, you can use `wget`:

Input
{: .label .label-green}
~~~
$ wget [file-address]
~~~
{: .shell-input}

