# VI-VIM-Basic to Advance
In this repo, I have covered all the option of vi-vim command used in linux.

▶ VI and VIM is a text editor used in linux.

▶ How to check VI or VIM command is available or not in your OS??
[student@redhatlab ~]$ which vi
/usr/bin/vi                      {If this output come that means VI is installed in your OS.}

[student@redhatlab ~]$ which vim
/usr/bin/which: no vim in (/home/student/.local/bin:/home/student/bin:/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin)      {VIM is not present in my OS}


▶ Package Required for VI  : **vim-minimal**-8.2.2637-20.el9_1.x86_64

▶ Package Required for VIM : **vim-enhanced**-8.2.2637-20.el9_1.x86_64

▶ How to Install the vim package if not found in the OS :- 
[student@redhatlab ~]$ sudo yum install vim-enhanced* -y

[student@redhatlab ~]$ which vim        ( To confirm VIM installed or not )
/usr/bin/vim               


▶ Types of mode in  vim editor ?
There are mainly three type of modes in vi/vim :- **01.)** INSERT MODE    **02.)** ESC MODE    **03.)** COMMAND OR COLON MODE

**Insert Mode**--->   to insert text into any file.

**ESC Mode**------>   to  perform any types of operation.
Example:  copy, paste, undo, redo, delete ...etc..

**Command or  Colon Mode**--->  to run any command.
Example:         :wq   (save and quit) 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
▶ Example of insert mode** 

 i             { to insert text before the cursor } 
 a             { to insert text after the cursor  }
 o             { to insert new line below of the cursor } 
 shit + o      { to insert line above of the cursor }


▶ Example of ESC  mode

 yy           { to copy any line } 
 p            { to paste the content }
 dd           { to delete any line }  
 u            { undo }
 ctrl + r     { redo }
 cc           { to cut copy any line } 
 yw	          { to copy any word }
 dw           { to delete any word }
 cw           { to cut copy word }
 p            { to paste the content}
 shift + d    { to delete line from the cursor }
 x 	          { to delete particular characters in forward side }
 shift + x    { to delete particular characters in backward side }
 shift + g    { to go in bottom of the file }
 gg	          { to move cursor in top of the file }
 zero         { to move cursor in begining of the line } {numeric zero }
 shift + $    { to move cursor in end of the line }
 b	          { to move cursor word by word in back side }   
 w	          { to move cursor word by word in forward side }
 /root	      { to search any pattern } 
              ( press n to jump on next pattern )
              ( press shift + n to jump on back pattern )


▶Example of command or colon mode

 :set number
   OR          { to set line number }
 :se nu

 :10          { to move cursor directly on any particular line number }
 :se nonu     { to remove line number }
 :se ic       { to deactivate the case-sensitive mode }
 /ROOT        { now it will work }
 :se noic     { to again activate the case-sensitive mode }
 :nohl	      { to remove highlight colors }
 :wq          { save and quit from any file }
      OR
 :x           { to save and quit from any file }
 :q!          { to quit without save }


***********************************************************************************************
▶ How to copy some lines from one file to another file using edit command ?
***********************************************************************************************
 # vim  passwd 

 5yy           { to copy five lines from your cursor}

 :edit  /report    ( Give the location of file in which you want to paste the copied content ) (press enter)

 p             { to paste the content }

 :wq   (press enter)

 # cat /report

***********************************************************************************************
▶ How to search and replace any word  ?
***********************************************************************************************
 # vim  passwd 

 :%s/root/network/g       {to replace root with network in every lines }

 :1s/network/root/g       { to replace network with root only in line number one }

 :1,13s/network/root/gi   { to replace network with root from 1 to 13 line number }

 :%s/nologin/bash/gic     { to confirm before replace any word }


 :wq     { Now we can save and quit from this file }

***********************************************************************************************
▶ How to set permanent line number for all files ?
***********************************************************************************************
[ root @ localhost ~ ] # vim  .vimrc

                        se nu  

                        :wq

 # vim  passwd
note:- Now you will  get automatically line numbers.


