Advanced CLI
============

The examples below will cover a few advanced CLI tools.  Use this as a reference, but be sure to go through these examples yourself.  Practice, practice, practice.

Advanced Bash/Zsh Commands
==========================

Environment Variables
---------------------

- Used for configuring a session
- Several built-in
- Can be customized, but will be lost upon log out

**printenv** - Displays all current environment variables

**echo $<env_name>** - Print a specific environment variable

    rico@verbal ~ $ echo $USER
    rico

**export <env_name>=<value>** - Set a new environment variable

    rico@verbal ~ $ echo $NOT_HERE
    
    rico@verbal ~ $ export NOT_HERE="Some Value"
    rico@verbal ~ $ echo $NOT_HERE
    Some Value

Aliases
-------

- Can be used to shorten complex commands
- Loads into current session, will be lost upon log out

**alias <short_value>='<long_value>'** - Set an alias

    rico@verbal ~/ $ alias my_val='cd ~/Projects/sandbox/test;cat test.txt;echo "My User: $USER"'
    rico@verbal ~/ $ my_val
    rico
    rico
    This is a test
    This is a test too
    My User: rico
    rico@verbal ~/Projects/sandbox/test $ 

VIM
---

- CLI Editor
- Highly Customizable
- Will capture entire terminal

**vim** - Command to access VIM

    rico@verbal ~/workspace/sandbox/test $ vim test.txt
    
The command above yields:

    rico
    rico
    This is a test
    This is a test too
    ~                                                                                  
    ~                                                                                  
    "test.txt" 4L, 44C

We will cover basic commands for editing. See a reference guide for more info. (i.e. https://vim.rtorr.com/)

**i** - Insert Mode (insert before the cursor).  From here you can edit with normal typing as you would expect from an editor.

**Esc** - Exit Insert Mode.  This is necessary to gain access to the editor commands.

**:w** - write (save) the file, but don't exit

**:wq** - write (save) and quit

**:q** - quit (fails if there are unsaved changes)

**:q!** - quit and throw away unsaved changes

There are several other useful commands that can be used in VIM, but the discovery of those are left up to the reader.

CURL
----

- Transfers a URL
- Supports HTTP, HTTPS, FTP, LDAP, etc...several
- See man page for more info

Examples:

    curl https://www.google.com

    curl https://content.uplynk.com/6a05152197df4bbcae2603fe4381af11.m3u8

    curl --header "Content-Type: application/json" https://content.uplynk.com/6a05152197df4bbcae2603fe4381af11.m3u8
    
RC Files
--------

- Custom behavior for application (if it expects an `.rc` file)
- Is a "dot" file (begins with `.`)
- Custom setup for each new session
- It is common for applications to use RC files for custom configurations. i.e. `.vimrc`

Example:

- .bashrc File (`less ~/.bashrc`)
- Set Environment variables
- Set aliases
- Run scripts
- Set terminal rules (color scheme, layout, etc)
