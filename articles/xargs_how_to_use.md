# xargs usage  
[Link](https://shapeshed.com/unix-xargs/)  
* "Command for building and executing command lines from standard input"
* "Whilst tools like grep can accept standard input as a parameter, many other tools cannot. Using xargs allows tools like echo and rm and mkdir to accept standard input as arguments."
* By default xargs reads items from standard input as separated by blanks and executes a command once for each argument.
## Using xargs with find
* "The most common usage of xargs is to use it with the find command. This uses find to search for files or directories and then uses xargs to operate on the results."
* e.g. echo 'one two three' | xargs rm // removes files
## Printing commands executed by xargs
* The -t option prints each command that will be executed to the terminal. 
	* e.g. echo 'one two three' | xargs -t rm
* The -p command will print the command to be executed and prompt the user to run it. This can be useful for destructive operations where you really want to be sure on the command to be run.
## How to run multiple commands with xargs
* It is possible to run multiple commands with xargs by using the -I flag. This replaces occurrences of the argument with the argument passed to xargs. 
* e.g. cat foo.txt | xargs -I % sh -c 'echo %; mkdir %' // The following prints echos a string and creates a folder.