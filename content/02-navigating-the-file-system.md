---
 layout: default
 title: Navigating the file system
 parent: Outline
 nav_order: 2
---
# Navigating the file system

Let's start by opening the unix shell. There are a few things you are likely to see right away. A cursor that is flashing next to a $ indicates where the command line begins. If you see the dollar sign it means that the command line is ready to take commands.

~~~
$
~~~

You are communicating with your computer by giving it commands and having it react to those commands.

## Orienting yourself
Let's enter our first command "pwd" which stands for "print working directory" and will tell us where we are in the system. The term "directory" refers to what you might visually think of as a "folder" when browsing your file system.

Input
{: .label .label-green}
~~~
$ pwd
~~~
Output
{: .label .label-yellow}
~~~
/Users/egrguric
~~~

Input
{: .label .label-green}
~~~
$ cd open .
~~~

![Finder window](finder.png)

Input
{: .label .label-green}
~~~
$ ls
~~~
Output
{: .label .label-yellow}
~~~
Applications		Downloads		Pictures
Creative Cloud Files	Library			Public
Desktop			Movies			Vagrants
Documents		Music
~~~

Input
{: .label .label-green}
~~~
$ ls -l
~~~
Output
{: .label .label-yellow}
~~~
total 0
drwx------@   3 egrguric  staff     96  6 Aug 14:25 Applications
drwx------+   6 egrguric  staff    192 21 Jan 22:04 Desktop
drwx------+  20 egrguric  staff    640 30 Dec 09:04 Documents
drwx------+ 527 egrguric  staff  16864 21 Jan 21:46 Downloads
drwx------@  71 egrguric  staff   2272 17 Oct 12:58 Library
drwx------+   3 egrguric  staff     96 18 Jul  2019 Movies
drwx------+   4 egrguric  staff    128  4 Sep 16:29 Music
drwx------+   4 egrguric  staff    128 25 Jul 13:56 Pictures
drwxr-xr-x+   4 egrguric  staff    128 18 Jul  2019 Public
~~~

Input
{: .label .label-green}
~~~
$ ls -lh
~~~
Output
{: .label .label-yellow}
~~~
total 0
drwx------@   3 egrguric  staff    96B  6 Aug 14:25 Applications
drwx------+   6 egrguric  staff   192B 21 Jan 22:04 Desktop
drwx------+  20 egrguric  staff   640B 30 Dec 09:04 Documents
drwx------+ 527 egrguric  staff    16K 21 Jan 21:46 Downloads
drwx------@  71 egrguric  staff   2.2K 17 Oct 12:58 Library
drwx------+   3 egrguric  staff    96B 18 Jul  2019 Movies
drwx------+   4 egrguric  staff   128B  4 Sep 16:29 Music
drwx------+   4 egrguric  staff   128B 25 Jul 13:56 Pictures
drwxr-xr-x+   4 egrguric  staff   128B 18 Jul  2019 Public

~~~

## Getting help
Commands come with instructions that you can access from the command line by invoking the "manual". You can also access this manual documentation online.

Input
{: .label .label-green}
~~~
$ man ls
~~~
Output
{: .label .label-yellow}
~~~

LS(1)                     BSD General Commands Manual                    LS(1)

NAME
     ls -- list directory contents

SYNOPSIS
     ls [-ABCFGHLOPRSTUW@abcdefghiklmnopqrstuwx1] [file ...]

DESCRIPTION
     For each operand that names a file of a type other than directory, ls
     displays its name as well as any requested, associated information.  For
     each operand that names a file of type directory, ls displays the names
     of files contained within that directory, as well as any requested, asso-
     ciated information.

     If no operands are given, the contents of the current directory are dis-
     played.  If more than one operand is given, non-directory operands are
     displayed first; directory and non-directory operands are sorted sepa-
     rately and in lexicographical order.

     The following options are available:

:
~~~
Notice the colon : which indicates that there is more text and you can keep paging through it by hitting "enter". To quit the manual hit the "q" key which stands for "quit".

You can only go to places that exist.

## Moving around

To move between directories we can use the "cd" command which stands for "change directory". This will move you one step forward in the system.

Input
{: .label .label-green}
~~~
$ cd Desktop
$ pwd
~~~
Output
{: .label .label-yellow}
~~~
/Users/egrguric/Desktop
~~~

When typing a directory name, the case of the directory doesn't matter on Mac or PC but does on Linux.

To move backwards in a directory use "cd .." which takes you back one step.

Input
{: .label .label-green}
~~~
$ cd ..
~~~
Output
{: .label .label-yellow}
~~~
/Users/egrguric
~~~
