Introduction to CLI
===================

The examples below will cover a wide range of common CLI tools.  Use this as a reference, but be sure to go through these examples yourself.  Practice, practice, practice.  

Bash/Zsh Commands
=================

**Use "Tab Complete" As Often As Possible!!**

**man** - Manual page.  Use this to get more information about any CLI tool.  *Note*: Some tools will use `-h` or `--help` instead.

**ctrl+u** - Clear the current command.

**ctrl+l** - Clear the screen. (Equivalent to **clear**)

**echo** - Display a line of text.

    rico@verbal ~ $ echo "Look at me!"
    Look at me!

**pwd** - Print Working Directory (where you are now)

    rico@verbal ~/Projects $ pwd
    /home/rico/Projects

**cd** - Change Directory

    rico@verbal ~/Projects $ cd
    rico@verbal ~ $

    rico@verbal ~ $ cd Projects/
    rico@verbal ~/Projects $ 

**ls** - List directory structure

    rico@verbal ~ $ cd Projects/
    rico@verbal ~/Projects $ 
    rico@verbal ~/Projects $ ls
    volicon-example

**ls -a** - List directory structure of all files (including "hidden" files/directories) 

    rico@verbal ~/Projects $ ls -a
    .  ..  volicon-example

**ls -l** - List directory structure (includes more info about the files/directories called "long listing format") 

    rico@verbal ~/Projects $ ls -a
    total 4
    drwxrwxr-x 2 rico rico 4096 Jul 11 08:22 volicon-example

**ls -al** - List directory structure of all files (to see more options try `man ls`) 

    rico@verbal ~/Projects $ ls -al
    total 12
    drwxrwxr-x  3 rico rico 4096 Jul 11 08:22 .
    drwxrwxr-x 18 rico rico 4096 Jul 11 08:14 ..
    drwxrwxr-x  2 rico rico 4096 Jul 11 08:22 volicon-example

**mkdir** - Make a directory

    rico@verbal ~/Projects $ mkdir sandbox
    rico@verbal ~/Projects $ ls
    sandbox       volicon-example

**touch** - Change file timestamps, change the access and/or modification times of the specified files.  Can be used as a shortcut to create an empty file.

    rico@verbal ~/Projects/sandbox $ ls
    rico@verbal ~/Projects/sandbox $ 
    
    rico@verbal ~/Projects/sandbox $ touch example_file.txt
    rico@verbal ~/Projects/sandbox $ ls
    example_file.txt
    
**rm** - Remove a file

    rico@verbal ~/Projects/sandbox $ ls
    example_file.txt
    rico@verbal ~/Projects/sandbox $ rm example_file.txt 
    rico@verbal ~/Projects/sandbox $ ls
    rico@verbal ~/Projects/sandbox $ 
    
**rmdir** - Safely removes a directory.  If the directory is not empty, it will warn and abort.

    rico@verbal ~/Projects/sandbox $ mkdir test
    rico@verbal ~/Projects/sandbox $ ls
    test
    rico@verbal ~/Projects/sandbox $ cd test
    rico@verbal ~/Projects/sandbox/test $ touch test.txt
    rico@verbal ~/Projects/sandbox/test $ cd ..
    rico@verbal ~/Projects/sandbox $ rmdir test
    rmdir: failed to remove 'test': Directory not empty
    rico@verbal ~/Projects/sandbox $ cd test
    rico@verbal ~/Projects/sandbox/test $ rm test.txt 
    rico@verbal ~/Projects/sandbox/test $ cd ..
    rico@verbal ~/Projects/sandbox $ rmdir test
    rico@verbal ~/Projects/sandbox $ ls
    rico@verbal ~/Projects/sandbox $ 

**>** - Redirect Output

    rico@verbal ~/Projects/sandbox/test $ whoami > test.txt 
    rico@verbal ~/Projects/sandbox/test $ cat test.txt 
    rico

**>>** - Redirect Output (concatenated)

    rico@verbal ~/Projects/sandbox/test $ whoami >> test.txt 
    rico@verbal ~/Projects/sandbox/test $ cat test.txt 
    rico
    rico
    
**cat** - Concatenates files and prints to STDOUT (standard out)

**less** - A file viewer (no editing)

**history** - A historical view of the commands used during this session.

**ctrl+r** - Reverse search for commands used in the history.

**tail** - Print the end of a file.

    rico@verbal ~/Projects/sandbox/test $ tail test.txt 
    rico
    rico

**tail -f** - Print the end of a file, forced open.  This is used for files that are repeatedly getting information added to it.

**grep** - Search the content of files for `regex` patterns.

    rico@verbal ~/Projects/sandbox/test $ cat test.txt 
    rico
    rico
    This is a test
    This is a test too
    rico@verbal ~/Projects/sandbox/test $ grep "rico" test.txt 
    rico
    rico
    
**find** - Find files on the system.

    rico@verbal ~/ $ find ~/Projects -name "test.txt"
    /home/rico/Projects/sandbox/test/test.txt

**ps** - A snapshot of the current processes (Too long to show.)

**|** - Pipe.  Used to pipe STDOUT into another CLI tool.

    rico@verbal ~/ $ ps -aux | grep "aux"
    rico     19837  0.0  0.0  39412  3352 pts/0    R+   10:33   0:00 ps -aux
    rico     19838  0.0  0.0  16272   948 pts/0    S+   10:33   0:00 grep --color=auto aux

**top** - Sustained display of processes.  (Too long to show.)
