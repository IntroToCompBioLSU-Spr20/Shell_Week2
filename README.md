# Paths, Terminal, and Bash commands

## Practicing with GitHub

- Have you created a GitHub username and sent it to me? If not, please do!

```
Practice Exercise - Copying and Editing a GitHub Repository

(1) Log into GitHub
(2) Go to class page
  - If you've accepted the invitation, you should see a link to the class page on your profile
(3) Go to this week's repository
(4) Click the "Fork" button in the upper right
(5) Find your copy of the repository in your profile and select it
(6) Once in the repository, click the "Create new file" button
(7) Give the file your name and in the body of the file, write your favorite biology fact.
(8) Scroll to the bottom and type an informative commit message
(9) Click the "Commit new file" button
(10) Once back on your repository page, click the "New pull request" button
** Now wait here until everyone is ready, and we'll discuss **

This is the general workflow for collaborative coding using GitHub.
```

A pull request is equivalent to asking the main repository to accept changes that you've made in your fork.

When using pull requests to submit assignments, make sure you're in the assignments folder.


## Paths to files and folders

- [Relative and absolute paths](https://github.com/IntroToCompBioLSU-Spr20/Intro_Week1/blob/master/Filesystems.md)

- Compare your answers to the practice exercise about paths with someone next to you. If your answers were different, discuss why.

## Practical Computing tips

- [Practical Computing Tips](https://github.com/IntroToCompBioLSU-Spr20/Intro_Week1/blob/master/ComputingTips.md)

## Your remote Linux computer

- LSU VPN (to work from off campus) - Available from TigerWare (Cisco VPN Client)

- [ondemand.mike.hpc.lsu.edu](https://ondemand.mike.hpc.lsu.edu)

```
Practice Exercise

(1) Log on to HPC OnDemand (any problems?)
(2) Go to Files -> Home Directory
(3) Look at the header bar at the top. What is the path to your home directory? - /home/harmonp/
(4) Using the "New File" and "New Dir" buttons at the top, create these
    directories and files in your home folder:
  - /home/<yourUserName>/myBiologyClasses - directory
  - /home/<yourUserName>/myBiologyClasses/CellBiology - directory
  - /home/<yourUserName>/myBiologyClasses/CellBiology/CellBioImportantNotes.txt - file
  - /home/<yourUserName>/myBiologyClasses/Ecology - directory
  - /home/<yourUserName>/myBiologyClasses/Ecology/EcologyImportantNotes.txt - file
  - /home/<yourUserName>/myBiologyClasses/Evolution - directory
  - /home/<yourUserName>/myBiologyClasses/Evolution/EvolutionImportantNotes.txt - file
(5) For each of your `.txt` files, click the "Edit" button, add some relevant text,
    and save your changes.
```

## Introduction to the Command Line

### Terminal

 - Built in to Linux (and Mac OS X)
 - By default,__usually__ uses the bash shell (interpreter)
 - The command prompt
 - Tab completion
 	- Double tapping tab will list all files with that beginning
 - Scrolling through history

### Commands related to navigating the filesystem

- `touch filename.txt` will create file
- `pwd` - print working directory - or - "where am I?"
- `ls` - list directory contents
- `ls -l` - long list
    - Everything has three types of permissions
        - Read
        - Write
        - Execute
    - And three groups whose permissions can be controlled
        - Owner
        - Group
        - Others
- [Wikipedia on Unix Permissions](https://en.wikipedia.org/wiki/File_system_permissions#Notation_of_traditional_Unix_permissions)
- la - list with hidden files
- `cd` - change directory
    - will accept absolute or relative paths
- `chmod` - change permissions - specify who (ugo), how (+ or -), and what (rwx)
- `man <command>` - gives us the manual page and options for any Unix command (q will get out of manual page)
- [Notes about command-line navigation](https://github.com/IntroToCompBioLSU-Spr20/Shell_Week2/blob/master/CommandLine_Navigating.md)

```
Practice Exercise

(1) Use the cd command to navigate up and down through the folders you created in the previous exercise.
(2) After each change of directory, use pwd to check the absolute path of your location.
(3) In folders with text files, use ls to examine the folder's contents.
```

### Commands related to files and folders

- `cp` - copies a file
    - `cp originalFile.txt newFile.txt`
- `mv` - moves __or__ renames a file
    - To change location, use paths: `mv myFile.txt ./folder/myFile.txt`
    - To change name, just use different names: `mv myFile.txt newName.txt`
- `cat filename.txt` - view file contents - can be called on multiple files and will conCATenate their contents
    - `cat file1.txt file2.txt file3.txt` will show all files in command line
    - `cat *.txt` shows all text in files with the file ending .txt
- `ls *.txt` show all files that end in .txt
    - `ls ../*.txt` go up one directory then tell me the txt files there (still within the same directory)
- `head -n #` - view the first # of lines of a file
- `tail -n #` - view the last # of lines of a file
- `less` - view the contents of a file a little at a time nice way to scroll through
- `touch filename.txt` - quickly create a new file
- `nano filename.txt` - this is actually an entire text editing program (type text like normal)
    - write out is save and ^=control (^O) exit (^X)
- `wc` - print out the length of a file in lines, words, and characters

```
Practice Exercise

(1) Create a file with the touch command.
(2) Make a copy of the file using cp.
(3) Rename the original version of the file to something else with mv.
(4) Use nano to add different text to each copy and save it.
(5) View the contents of each file with cat.
(6) Check the sizes of each file with wc.
```

- `echo` - prints something to the screen (or elsewhere, as directed)
- `>>` - appends to file
    - `echo "some text here" >> myTextFile.txt`
- `>` - writes to (or over!) file
    - `echo "more text here" > myTextFile.txt`
- __WARNING - BIG WARNING - PAY ATTENTION__ - `rm` _permanently_ removes a file
    - No going back - always use this VERY carefully
    - I know people who've accidentally erased their __entire computers__ using this command
    - `rm -r` recursively removes a directory and everything inside it - even more dangerous than just `rm`!
    - This is the reason permissions are so important. If someone doesn't have write permissions on a file or folder, they shouldn't be able to delete it.
- `mkdir MyDirectory` - create a new (empty) directory (folder)
- `rmdir MyDirectory` - remove an empty directory !!WARNING!!
- wildcards - * is especially useful - matches anything
- `grep` - find only lines matching some particular string

```
Practice Exercise

(1) Create a series of new text files, with some filenams starting with one letter and some starting with another.
(2) Use echo and output redirection (> or >>) to add content to the files.
(3) With one command, list all the files that start with one particular letter.
(4) Make a new directory
(5) Move all files that start with one particular letter into the new directory.
(6) Try to remove that directory with rmdir. Can you?
(7) Extract all the lines from the files you created that contain one particular word of your choosing.
```

- [Notes about editing files and folders from the command line](https://github.com/IntroToCompBioLSU-Spr20/Shell_Week2/blob/master/CommandLine_Editing.md)

### Commands related to the Unix environment

- Can create a variable and assign value using `=`
    - `myVariable=2`
- Can print value of variable using `echo` and starting name with `$`
    - `echo $myVariable`
- `|` - the Unix pipe can be used to send the output of one command into the input of another
    - `history | tail -n 20 >> endOfHistory.txt`


```
Assignment 2

(1) Log on to SuperMike2 using OnDemand (https://ondemand.mike.hpc.lsu.edu/).
(2) Open a Terminal window (Clusters -> SuperMike-II Shell Access)
(3) Change directories to the root of the filesystem
(4) List the contents of the root directory
(5) Copy and paste these contents into a text file on your local computer.
(6) If you haven't already, fork the Week 2 repository for this class on GitHub.
(7) In your fork, create a new file in the Week2Assignments folder (the name of
  the file should include your name). Then paste the contents of the SuperMike
  root folder that you listed in step (4).
(8) Commit this new file.
(9) Submit a pull request back to the class page with your new file.

Complete before class on Tuesday, January 28th.
```
