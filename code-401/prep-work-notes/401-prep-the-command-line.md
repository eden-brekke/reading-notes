# The Command Line

## Tasks

Working as a tech professional will often involve interacting with the terminal on your computer.

This pre-work will introduce you to some of the more common commands involved in traversing directories and manipulating files on your computer.

[Bash Command Line Tutorials](https://ryanstutorials.net/linuxtutorial/)

* [The Command Line](https://ryanstutorials.net/linuxtutorial/commandline.php) - What is it, how does it work and how do I get to one.
  * :)
  * What is a command line? A text based interface to the system. Where you can enter commands by typing.
  * Opening the command line, since I'm on windows I use a virtual machine and use the terminal Ubuntu
  * Within the terminal is known as the shell, thats the part of the OS that defines how the terminal will behave and look after it executes a command for you. Most common shell is bash but I use oh my zsh
  * There are many shortcuts to make terminal work easier, the first they give is that you can use arrow keys to traverse your history so you don't need to retype a command you've already typed recently. 
* [Basic Navigation](https://ryanstutorials.net/linuxtutorial/navigation.php) - An introduction to the Linux directory system and how to get around it.
  * :)
  * First command they teach us is pwd: print working directory. It tells you where you are in your computer(directory)
  * Next Command is ls which is short for list. Tells you the contents of the directory you're in
    * You can add options and locations to your list command.
    * ls -l will do a command for long listing
    * ls /etc will tell the list not to list our current directory but instead to list the directories contents
      * the two above optional commands (-l and /etc) can be used together: ls -l /etc
  * Jumpin into paths:
    * two types of paths: Relative and Absolute
    * Absolute paths specify a location (file or directory) in relation to the root directory (they always begin with /)
      * An example is : ls /home/eden/Documents
    * relative paths specify a location in relation to where we currently are in the system and don't begin with a /
      * An example is : ls Documents (So long as I'm cd'd into /home/eden)
    * ~ is a shortcut to hop back to the home directory
    * . is a reference to your current directory
    * .. is a reference to the parent directory
  * Shortcut: if you run the command cd without any arguments it will always take you back to your home directory.
  * Shortcut: Tab completion, pressing tab will invoke the autocomplete action

* [More About Files](https://ryanstutorials.net/linuxtutorial/aboutfiles.php) - Find out some interesting characteristics of files and directories in a Linux environment.
  * :)
  * In the linux system everything is a file! Even your keyboard and monitor
  * Linux is an extensionless system. In Windows extensions are important. But Linux ignores this.
  * Linux is case sensitive with it's files. So FILE1 File1 and file1 would all be different files in linux whereas they would not be in windows
  * You can use spaces inf ile and directory names but it makes using the command line more difficult cause a space is how you separate items.
    * You can work around this if you have spaces in your file name with quotes 'Holiday Photos' "Holiday Photos" or with escape characters Holiday\ Photos.
    * If you use Tab completion with space named files/directories the auto complete will add escape characters for you.
  * if a file is hidden the file will start with a . and if you want to list them you add the command -a (-all) to the end of ls (ls -a)
* [Manual Pages](https://ryanstutorials.net/linuxtutorial/manual.php) - Learn how to make the most of the Linux commands you are learning.
  * :)
  * What are Manual Pages? A set of pages that explain every command available on your system and what they do.
    * man ls (example)
  * to exit man pages press q for quit
  * searching can be done with: man -k search term
  * ls -alh means list all author human readable
  * you can use n to select an item within the manual page
* [File Manipulation](https://ryanstutorials.net/linuxtutorial/filemanipulation.php) - How to make, remove, rename, copy and move files and directories.
  * :)
  * Command mkdir to make a directory 
  * mkdir -p tells mkdir to make parent directories as needed
  * mkdir -v tells mksir to tell us what it is doing
    * you can use -pv together
  * rmdir will remove a directory
  * touch will create a blank file
  * cp options source destination will copy a file from one place to another
  * mv options source destination will move a file form one place to another
    * you can use mv to rename a file as well
  * rm options file to remove a file (not a directory)
  * there is no undo feature, so you should perform destructive actions carefully
* [Cheat Sheet](https://ryanstutorials.net/linuxtutorial/cheatsheet.php) - A quick reference for the main points covered in this tutorial.
  * :)
  * pwd : where am I? (**internal panic rising**)
  * ls : list items in directory, common options -l -h -a
  * cd : change directory
  * path : description of where a file/directory is within the system
  * absolute path : beginning from root
  * relative path : relative to where you currently are in system
  * ~ bring you back home
  * . current directory
  * .. parent directory
  * Tab completion, press tab to invoke auto completion
  * file path : find out type of file
  * spaces in name can be worked around with quotes or escape character \
  * hidden files have a . in front of the name
  * man : shows you manual for the command
  * man -k search term : search pages for the term 
  * press q to quit man pages
  * mkdir : makes a directory
  * rmdir : removes a directory
  * touch : creates a file
  * cp : copy a file from a place to another place
  * mv : moves a file from a place to another place
  * rm : removes a file common options -r and -f