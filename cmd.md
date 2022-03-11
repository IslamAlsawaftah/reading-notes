 # Command Line

 ##### Is a text based interface to the system, use to save our time, we can have several command lines open and doing different tasks in each at the same time.
 ##### Opening a terminal(Linux): Applications -> System or Applications -> Utilities. Alternatively you may be able to 'right-click' on the desktop and there may be an option 'Open in terminal'.
 ##### To know which shell you are using you may use a command called echo to display a system variable stating your current shell. echo is a command which is used to display messages.

 ### Baic Commands:
 * pwd which stands for Print Working Directory. It tells you what your current or present working directory is.
 * ls when we want to know what is there. It's short for list
 * cd move around in the system which stands for change directory
 * Relative path A file or directory location relative to where we currently are in the file system.
 * Absolute path A file or directory location in relation to the root of the file system. building blocks help build paths,like:
   * ~ (tilde) - This is a shortcut for your home directory. eg, if your home directory is /home/ryan then you could refer to the directory Documents with the path /home/ryan/Documents or ~/Documents
   * . (dot) - This is a reference to your current directory. eg in the example above we referred to Documents on line 4 with a relative path. It could also be written as ./Documents (Normally this extra bit is not required but in later sections we will see where it comes in handy).
   * .. (dotdot)- This is a reference to the parent directory. You can use this several times in a path to keep going up the hierarchy. eg if you were in the path /home/ryan you could run the command ls ../../ and this would do a listing of the root directory.

### Files
* file obtain information about what type of file a file or directory is.
* ls -a List the contents of a directory, including hidden files.

Everything is a file under Linux,Even directories.
Linux is an extensionless system : Files can have any extension they like or none at all.
Linux is case sensitive: Beware of silly typos.
Escape Characters : escape (or nullify) the special meaning of the next character..

### Manual Pages: 
##### are a set of pages that explain every command available on your system including what they do, the specifics of how you run them and what command line arguments they accept.search within a manual page this is also possible.Instead of trying to remember everything, instead remember you can easily look stuff up in the man pages.
- man `<command>` Look up the manual page for a particular command.
- man -k `<search term>` Do a keyword search for all manual pages containing the given search term.
- `/<term>` Within a manual page, perform a search for 'term'
- n After performing a search within a manual page, select the next found item.

###File Manipulation
- mkdir Make Directory - ie. Create a directory.
- rmdir Remove Directory - ie. Delete a directory.
- touch Create a blank file.
- cp Copy - ie. Copy a file or directory.
- mv Move - ie. Move a file or directory (can also be used to rename).
- rm Remove - ie. Delete a file.
- No undo The Linux command line does not have an undo feature. Perform destructive actions carefully.
- Command line options Most commands have many useful command line options. Make sure you skim the man page for new commands so you are familiar with what they can do and what is available.
[Cheatsheet](https://ryanstutorials.net/linuxtutorial/cheatsheet.php)