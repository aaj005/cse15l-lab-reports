# lab 1 

## cd command 

*no arguments* 
[user@sahara ~]$ cd
Since I did not specify a directory to change to, my directory remained the same. It is not an error exactly, but nothing changed. 

*directory argument*
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ 
when I put in a directory as an argument, my current directory changed to lecture1. This is not an error. 

*file argument*
[user@sahara ~]$ cd lecture1/messages/en-us.txt
bash: cd: lecture1/messages/en-us.txt: Not a directory
When I put in a path to a file as an argument, I received an error. This is because you cannot set your directory to a file. It must be set to another directory. 

## ls command

*no arguments*
[user@sahara ~]$ ls
lecture1
When I did not put in an argument, it displayed all directories under my current one. This is not an error.

*directory argument*
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
When I put in a directory as an argument, it displayed all directories and files in the directory that I specified. This is not an error.

*file argument*
[user@sahara ~]$ ls lecture1/messages/ro.txt
lecture1/messages/ro.txt
When I put in a path to a file as an argument, it displayed the path to the file. This is not an error, but the command does not have the capacity to display the contents of the file. 

## cat command

*no arguments* 
[user@sahara ~]$ cat
Running the command without an argument froze the terminal. This error occured because no file was specified to be read. 

*directory argument*
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
Running the command with a directory as an argument also gave an error. This is because the cat command is meant to read files. 

*file argument*
[user@sahara ~]$ cat lecture1/messages/en-us.txt
Hello World!
When given the path to a file as an argument, the cat command displayed the contents of the file. This is not an error. 
