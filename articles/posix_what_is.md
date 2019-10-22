# What exactly is POSIX?  
**Definition**: POSIX is a family of standards, specified by the IEEE.  
**Purpose**: to clarify and make uniform the application programming interfaces (and ancillary issues, such as commandline shell utilities) provided by Unix-y operating systems  
## Great answer on Stack 
[Link](https://stackoverflow.com/a/31865755/6708274)  
* C API (extension of ANSI C)
	* functions like: mkdir, dirname, symlink, link, stat, sync, kill, fork, pipe, sleep etc.
* CLI utilities
	* cd, ls, echo, sed, grep awk
* Shell language
	* a=b; echo "$a"
* Environmental variables
	* HOME, PATH etc.
* Program exit status
	* 0 on EXIT_SUCCESS etc.
	* 127: command not found
	* >128 terminated by a signal
* Regular Expression
	* There are two types: BRE (Basic) and ERE (Extended). Basic is deprecated. 
* Directory structure
	* e.g. /dev/null, /tmp etc.
	* Linux FHS (FIlesystem Hierarchy Standard) greatly extends POSIX
* Filenames
	* / is path separator
	* NUL cannot be used
	* . cwd .. etc.
* Command line utility API conventions
	* - stdin where file is expected
	* -- terminates flags e.g. ls -- -l to list a directory named -l
## Who follows POSIX?
* Many systems follow POSIX closely, but few are actually certified by the Open Group which maintains the standard. Notable certified ones include:
	* OS X (Apple) X 
	* AIX (IBM)
	* Solaris (Oracle)