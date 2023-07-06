# 0x01-shell_permissions 

## 0-iam_betty :

a script that switches the current user to the user betty .

## 1-who_am_i :

a script that prints the effective username of the current user.

## 2.groups :

a script that prints all the groups the current user is part of.

## 3-new_owner :

a script that changes the owner of the file hello to the user betty.

## 4-empty : 

a script that creates an empty file called hello.

## 5-execute :

a script that adds execute permission to the owner of the file hello.

## 6-multiple_permissions :

a script that adds execute permission to the owner and the group owner, and read permission to other users, to the file hello.

## 7-everybody :

a script that adds execution permission to the owner, the group owner and the other users, to the file hello

	The file hello will be in the working directory
	
	You are not allowed to use commas for this script

## 8-James_Bond :

a script that sets the permission to the file hello as follows:

	Owner: no permission at all

	Group: no permission at all

	Other users: all the permissions
	
	The file hello will be in the working directory You are not allowed to use commas for this script

## 9-John_Doe :

a script that sets the mode of the file hello to this:

	-rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello

	The file hello will be in the working directory

	You are not allowed to use commas for this script

## 10-mirror_permissions :
Write a script that sets the mode of the file hello the same as olleh’s mode.

	The file hello will be in the working directory

	The file olleh will be in the working directory


