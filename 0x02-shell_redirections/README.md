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

## 100-empty_casks :

Write a command that finds all empty files and directories in the current directory and all sub-directories.

	Only the names of the files and directories should be displayed (not the entire path)
		
	Hidden files should be listed
	
	One file name per line
		
	The listing should end with a new line
	
	You are not allowed to use basename, grep, egrep, fgrep or rgrep
solution :

the command `find . -empty | rev | cut -d '/' -f 1 | rev` 

	- `find . -empty`: This command finds empty files and directories starting from the current directory (`.`).
	
	 The `-empty` option matches empty files or directories. 
		
		{didn't use -not -name '.' as we need to search in the current directory itself also not only the directories on it }

	- `rev`: This command reverses each line of input. It is used here to reverse the output of `find` so that the file or directory name appears at the beginning of the line.

	- `cut -d '/' -f 1`: This command cuts each line at the delimiter `/` and selects the first field. By using `/` as the delimiter, it effectively removes the path and retains only the file or directory name.

	- `rev`: Finally, the `rev` command is used again to reverse the lines back to their original order.

The result is that the command will find empty files and directories, extract only their names (without the path), and display them on separate lines.

Please note that while this command accomplishes the same task, it is more convoluted compared to the previous command that utilizes the `-printf` option of `find`.

##  101-gifs :

Write a script that lists all the files with a .gif extension in the current directory and all its sub-directories.

	Hidden files should be listed

	Only regular files (not directories) should be listed

	The names of the files should be displayed without their extensions

	The files should be sorted by byte values, but case-insensitive (file aaa should be listed before file bbb, file .b should be listed before file a, and file Rona should be listed after file jay)
	
	One file name per line

	The listing should end with a new line

	You are not allowed to use basename, grep, egrep, fgrep or rgrep

solution :

	Certainly! Here's an explanation of the provided command:


	- `find -type f -name "*.gif"`: This command utilizes the `find` utility to search for regular files (`-type f`) with the extension `.gif` in the current directory and its subdirectories.


	- `rev`: The output of the previous command is piped (`|`) to the `rev` command. This reverses the order of characters in each line.


	- `cut -d "/" -f 1`: The output of `rev` is piped to the `cut` command, which uses the `/` character as the delimiter (`-d "/"`) and extracts the first field (`-f 1`), effectively removing the directory path and leaving only the file names.


	- `cut -d "." -f 2-`: The output of the previous `cut` command is then piped to another `cut` command. This time, the `.` character is used as the delimiter (`-d "."`). By specifying `-f 2-`, it extracts all fields starting from the second field, effectively removing the extension from the file names.


	- `rev`: The output of the second `cut` command is piped to `rev` again, reversing the order of characters back to their original form.


	- `LC_ALL=C sort -f`: this command is used to sort the output of the previous pipeline (`rev | cut -d "." -f 2- | rev`) in a case-insensitive manner using byte values.

Explanation:

- `sort -f`: This command sorts the input in lexicographical order, with case-insensitive comparisons. The `-f` option tells `sort` to perform a case-insensitive sort.

- `LC_ALL=C`: This is an environment variable setting that modifies the locale for the `sort` command. By setting `LC_ALL=C`, it ensures that the sorting is done using the C locale, which uses byte values for sorting characters. This guarantees a consistent sorting order, regardless of the system's default locale settings.

Combining `LC_ALL=C` with `sort -f` ensures that the sorting is case-insensitive and based on byte values. This is particularly useful when dealing with filenames that might contain characters with different case sensitivities or accented characters.

##  102-acrostic :

An acrostic is a poem (or other form of writing) in which the first letter (or syllable, or word) of each line (or paragraph,
 or other recurring feature in the text) spells out a word, message or the alphabet.
 The word comes from the French acrostiche from post-classical Latin acrostichis). 
As a form of constrained writing, an acrostic can be used as a mnemonic device to aid memory retrieval.

###  Create a script that decodes acrostics that use the first letter of each line.

	The ‘decoded’ message has to end with a new line

	You are not allowed to use grep, egrep, fgrep or rgrep

Solution Explaination :

The command `cut -c 1 | paste -s -d ''` performs some operations on the input it receives. Let's break it down step by step:

- `cut -c 1`: This command uses the `cut` utility to extract the first character (`-c 1`) from each line of input. It selects only the first character of each line.

- `paste -s -d ''`: This command is used to concatenate the output of `cut` into a single line, with no delimiter between characters. Here's what each option does:

When you combine these two commands using the pipe (`|`) symbol, the output of `cut -c 1` becomes the input for `paste -s -d ''`. The `cut` command extracts the first character from each line, and then `paste` concatenates those characters into a single line with no delimiter.


In summary, the `cut -c 1 | paste -s -d ''` command takes input, extracts the first character from each line, and concatenates them into a single line without any delimiter.

##  103-the_biggest_fan :

Write a script that parses web servers logs in TSV format as input and displays the 11 hosts or IP addresses which did the most requests.

	Order by number of requests, most active host or IP at the top

	You are not allowed to use grep, egrep, fgrep or rgrep

Solution Explaination :

- `tail -n +2`: This command skips the first line of input and outputs the rest. The `-n +2` option tells `tail` to start from the second line.

- `cut -f -1`: This command extracts the first field from each line using the delimiter specified by the `-d` option. In this case, the delimiter is the tab character by default.

- `sort -k 1`: This command sorts the input based on the first field.

- `uniq -c`: This command counts the number of occurrences of each unique line and displays it along with the line.

- `sort -rnk 1`: This command performs a reverse numeric sort based on the first field in descending order. The `-r` option indicates a reverse sort, and the `-n` option ensures the sorting is numeric.

- `head -n 11`: This command outputs the first 11 lines of the input.

- `rev`: This command reverses the order of characters in each line.

- `cut -d ' ' -f -1`: This command extracts the first field from each line using a space (' ') as the delimiter.

- `rev`: This command reverses the order of characters back to their original form.




