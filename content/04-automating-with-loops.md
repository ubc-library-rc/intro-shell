---
 layout: default
 title: Automating with loops
 parent: Outline
 nav_order: 3
---

# Automating with loops

Sometimes you want to do a lot quickly. Loops are a way to automate a series of commands so that you batch together.

The structure of a loop is:

~~~
for thing in list_of_things
do
  operation_using $thing #Indentation is not required but helps legibility.
done
~~~

Applied in an example, this looks like:

~~~
for filename in *.doc
do
  echo "$filename"
  cp "$filename" backup_"$filename"
done
~~~

Notice that as you write a loop in the shell the indicator changes from $ to > which essentially means "waiting for the command to finish".

In this example we are saying that every time a filename has the ".doc" extension, we want to take the name of the file, and then make a copy of it while prefixing the file with "backup_". The result is a backup of every file with a .doc extension in our directory.

Let's say we make four files called one.doc, two.doc, three.doc, and four.doc.

Input
{: .label .label-green}
~~~
touch one.doc two.doc three.doc four.doc
~~~
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
for filename in *.doc
> do
>   echo "$filename"
>   cp "$filename" backup_"$filename"
> done
~~~
Output
{: .label .label-yellow}
~~~
four.doc
one.doc
three.doc
two.doc
~~~

If we now ls in the working folder we see the four backup files.

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
