Q & A Notes
===========

Throughout the training there are going to be questions.  This is a place where we can note the question and the corresponding answer, for posterity.  

1. Next and Previous for regex searching in less.

        This information can be found in the man page.  n - for next, N - for previous
        
2. What are the bits for permissions on files and directories?

        It can be interpretted as user:group:everyone and is set as r - read, w - write, x - execute.
        Consider 7, in binary as 111 - This sets all bits to active and will be readable, writable and executable.
        Likewise 4 in binary is 100 - This sets the read bit and sets the file as read only.
        The user, group and everyone is set separately.  So, 423 would be r---w-r-x, which would allow the user to read, the group to write and everyone to read and execute.  (this isn't a particularly useful setting, used only for an example)
        
        
