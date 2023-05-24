---
 layout: default
 title: What is the shell?
 parent: Outline
 nav_order: 1
---

# What is the shell?
<em><a href="../slides/introduction.html" target="_blank">View slides</a> for this section</em>

The shell (sometimes referred to as the **Unix shell**, for the operating system where it was first developed) is a program that allows you to interact with your computer using typed text commands. It is the primary interface used on Linux and Unix-based systems, such as macOS, and can be optionally installed on other operating systems such as older versions of Windows. As of Windows 10 the Unix shell comes pre-installed but must be turned on.

The most popular Unix shell is Bash (the Bourne Again SHell). Using the shell has a steep learning curve compared with the GUI. While a GUI presents you with choices to select, the command-line interface (CLI) does not present the choices to you. The syntax of the shell allows you to make powerful pipelines by coupling existing commands and handling repetitive tasks. Many shells support scripting as well.

In addition, the command line is often the best option to interact with remote machines and servers. As clusters and cloud computing systems become more common, researchers need to learn the necessary skills to tackle file handling and job submission tasks.

## Why should I use it?

Most of the time when we work with files on a computer the graphical user interface (GUI) that we are familiar with does the job. This is how we visually navigate, scroll, and click through information on our computers.

It's when we are dealing with a large number of files or folders that are scattered across many different locations that the shell is very useful. Any time that you need to do something very repetitive to a large number of files, for example renaming everything in a folder or separating out all of a certain type of file, there is likely a way to use the shell to speed up your work.

## How do I get to it?

For Mac and Linux, which are Unix-based systems, you can access the Unix shell through an application called "Terminal". It is findable like any other piece of software installed on your computer.

Windows 10 users have the option to enable the Unix shell, which is already integrated into the operating system. You can find more information in [Simplified Installation](https://docs.microsoft.com/en-us/windows/wsl/install-win10#simplified-installation-for-windows-insiders). For older versions of Windows, such as Windows 7 or Windows 8, the Unix shell is not natively available as part of the operating system. However, you can use the bash emulation layer provided in the command line installed with [Git Bash](https://git-scm.com/download/win).

[Windows Power Shell](https://learn.microsoft.com/en-us/powershell/scripting/overview?view=powershell-7.2) and [Command Prompt](https://en.wikipedia.org/wiki/Cmd.exe) are traditional terminal applications that may have limitations when it comes to user-friendliness and features. They lack multi-tab functionality, may not fully support UTF-8 characters, and have a limited set of features compared to modern terminal applications.

For a better terminal experience on Windows, we recommend installing [Windows Terminal](https://apps.microsoft.com/store/detail/9N0DX20HK701?hl=en-ca&gl=CA). It is a robust and contemporary terminal application that offers a more intuitive and feature-rich environment. Windows Terminal supports multiple tabs, allowing you to work with multiple command-line sessions simultaneously. It also provides extensive customization options, enabling you to personalize the appearance and behavior of your terminal. Additionally, Windows Terminal supports UTF-8 characters, ensuring compatibility with a range of languages and character sets.