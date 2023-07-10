# 0x02-shell_redirections :

## 0-hello_world :

a script that prints “Hello, World”, followed by a new line to the standard output.

##  1-confused_smiley :

a script that displays a confused smiley "(Ôo)'.

##  2-hellofile :

Display the content of the /etc/passwd file.

##  3-twofiles :

Display the content of /etc/passwd and /etc/hosts .

## 4-lastlines :

Display the last 10 lines of /etc/passwd .

##  5-firstlines :

Display the first 10 lines of /etc/passwd .

##  6-third_line :

a script that displays the third line of the file iacta.

The file iacta will be in the working directory

You’re not allowed to use sed .

##  7-file :

a shell script that creates a file named exactly
 \*\\'"Best School"\'\\*$\?\*\*\*\*\*:) 
containing the text Best School ending by a new line.

## 8-cwd_state :

a script that writes into the file ls_cwd_content the result of the command ls -la. If the file ls_cwd_content already exists, it should be overwritten. If the file ls_cwd_content does not exist, create it.

## 9-duplicate_last_line :

a script that duplicates the last line of the file iacta

	The file iacta will be in the working directory .

## 10-no_more_js :

a script that deletes all the regular files (not the directories) with a .js extension that are present in the current directory and all its subfolders.

##  11-directories :

a script that counts the number of directories and sub-directories in the current directory.

	The current and parent directories should not be taken into account
	Hidden directories should be counted
solution :

1. `find . -type d`: This command uses the `find` utility to search for directories (`-type d`) starting from the current directory (`.`). The dot (`.`) represents the current directory. This command will list all directories recursively.

2. `-not -name '.'`: This part of the command is used to exclude the current directory (`.`) from the results. The `-not` option negates the following expression, and `-name '.'` specifies that the name should not be a dot (`.`).

3. `|`: This is called a pipe symbol. It is used to redirect the output of the previous command as input to the next command.

4. `wc -l`: This command stands for "word count" and is used to count the number of lines in the input. The `-l` option tells `wc` to count lines.

So, when you put it all together, the command `find . -type d -not -name '.' | wc -l` searches for directories starting from the current directory, excludes the current directory itself, and then counts the number of directories found (excluding the current directory).


##  12-newest_files :

a script that displays the 10 newest files in the current directory.

Requirements:

	One file per line
	Sorted from the newest to the oldest

'ls -t1' : This command lists the contents of the current directory (ls) in a sorted manner by modification time (-t) in descending order, 
with one file per line (-1).


## 13-unique :

a script that takes a list of words as input and prints only words that appear exactly once.

	Input format: One line, one word
	Output format: One line, one word
	Words should be sorted

'uniq -u' : The uniq command is used to filter adjacent duplicate lines from its input.
The -u option is used to display only the unique lines, i.e., it removes any duplicate lines from the sorted input.

##  14-findthatword :

Display lines containing the pattern “root” from the file /etc/passwd

##  15-countthatword :

Display the number of lines that contain the pattern “bin” in the file /etc/passwd

solution :
	grep -i "bin" /etc/passwd |wc -l

or can use that code ,it do the same 

	grep -c -i "bin" /etc/passwd

##  16-whatsnext :

Display lines containing the pattern “root” and 3 lines after them in the file /etc/passwd.

' -A 3  '  option: Specifies that we want to display three lines after each match. 
The -A (after) option is used to specify the number of lines to include after each matching line.

##  17-hidethisword :

Display all the lines in the file /etc/passwd that do not contain the pattern “bin”.

##  18-letteronly :

Display all lines of the file /etc/ssh/sshd_config starting with a letter.

	include capital letters as well

Solution Explanation:

grep: The command used for searching patterns in files.

"^[[:alpha:]]": The regular expression pattern we want to match.

^ indicates the start of a line.

[[:alpha:]] represents any alphabetic character, including both lowercase and uppercase letters.

/etc/ssh/sshd_config: The file in which we want to search for the pattern.

When you run this command, it will search for lines in the /etc/ssh/sshd_config file that start with a letter (including both lowercase and uppercase letters) and display those lines.

##  19-AZ :

Replace all characters A and c from input to Z and e respectively.

##  20-hiago :

Create a script that removes all letters c and C from input.

##  21-reverse :

Write a script that reverse its input.

##  22-users_and_homes :

Write a script that displays all users and their home directories, sorted by users.

	Based on the the /etc/passwd file


