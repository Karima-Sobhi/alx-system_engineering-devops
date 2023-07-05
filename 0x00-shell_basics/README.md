# Shell Basics In a Nutshull 
## 0-current_working_directory :

a script that prints the absolute path name of the current working directory.

## 1-listit :

Display the contents list of your current directory.

## 2-bring_me_home :

a script that changes the working directory to the user’s home directory.

## 3-listfiles :

Display current directory contents in a long format.

## 4-listmorefiles :

Display current directory contents, including hidden files (starting with .). Use the long format.

## 5-listfilesdigitonly :

Display current directory contents.



    Long format


    with user and group IDs displayed numerically


    And hidden files (starting with .)


## 6-firstdirectory :

Create a script that creates a directory named my_first_directory in the /tmp/ directory.

## 7-movethatfile :

Move the file betty from /tmp/ to /tmp/my_first_directory.

## 8-firstdelete :

Delete the file betty.

    The file betty is in /tmp/my_first_directory.

## 9-firstdirdeletion : 

Delete the directory my_first_directory that is in the /tmp directory.

## 10-back :

Write a script that changes the working directory to the previous one.

## 11-lists :

a script that lists all files (even ones with names beginning with a period character, which are normally hidden) in the current directory and the parent of the working directory and the /boot directory (in this order), in long format.

## 12-file_type :

a script that prints the type of the file named iamafile. The file iamafile will be in the /tmp directory when we will run your script.

## 13-symbolic_link :

Create a symbolic link to /bin/ls, named __ls__. The symbolic link should be created in the current working directory.

## 14-copy_html :

Create a script that copies all the HTML files from the current working directory to the parent of the working directory, but only copy files that did not exist in the parent of the working directory or were newer than the versions in the parent of the working directory.

You can consider that all HTML files have the extension .html

## 100-lets_move :

Create a script that moves all files beginning with an uppercase letter to the directory /tmp/u.
You can assume that the directory /tmp/u will exist when we will run your script

## 101-clean_emacs :

 a script that deletes all files in the current working directory that end with the character ~.

## 102-tree :

Create a script that creates the directories welcome/, welcome/to/ and welcome/to/school in the current directory.
You are only allowed to use two spaces (and lines) in your script, not more.

## 103-commas :

To list all the files and directories of the current directory, separated by commas (,).

	Directory names should end with a slash (/)
    
	Files and directories starting with a dot (.) should be listed
    
	The listing should be alpha ordered, except for the directories . and .. which should be listed at the very beginning
    
	Only digits and letters are used to sort; Digits should come first
    
	You can assume that all the files we will test with will have at least one letter or one digit
    	
	The listing should end with a new line

## school.mgc :

Create a magic file school.mgc that can be used with the command file to detect School data files. School data files always contain the string SCHOOL at offset 0.


This exercise was much different from the previous exercises. 

From what I understand, the magic file is used to detect patterns in files and will give a specified output depending on a matching pattern. 

The first argument is a number representing the offset. 

The second argument is the data type you are searching for. In our case, it is a string. 

The third argument is the data you are searching for. In our case, "SCHOOL", which we specified as a string in the second argument. 

The fourth argument is the message you want to output on match. If the search matches, it will output this message. 

The last argument is separated by a line. Since the fourth argument can be long and contain multiple strings, we separate the fourth and fifth arguments with this new line. 

This last argument can be multiple different things. 

In this case, a MIME type. According to bash manual, a "MIME type is given on a separate line, which must be the next non-blank or comment line after the magic line that identifies the file type".

 I knew to search for a MIME type because the example provided: $ file --mime-type -m School.mgc * The above returns message "School" when matching a MIME ?? Not exactly sure, but this is what I can tell from what I've tested out and can see from the output and examples. 

$ file -m school.mgc * The above will return message "School data" for any offset 0 "SCHOOL" matches. 

A cool thing to note is that the file command is compiling and running the magic file. So there is no need to compile to magic "permanently".

 NOTE: Compiling a magic source file: $ file -C -m .mgc This produces the compiled magic file.

$ file -i -m .mgc * This allows you to use the compiled file by specifying its name using the -m switch again.

