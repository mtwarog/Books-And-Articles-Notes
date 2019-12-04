# Bash MAN page - part I  
**Definition**: Bash  is  an sh-compatible command language interpreter that executes commands read from the standard input or from a file.  
## Environment
* When a program is invoked it is given an array  of  strings  called  the  environment. This  is  a  list  of name-value pairs, of the form name=value.
* The  shell  provides several ways to manipulate the environment.  On invocation, the shell scans its own environment and creates a parameter for each name found, automatically marking it for export to  child  processes.
* Executed  commands inherit the environment.
## Exit status
* The  exit  status  of an executed command is the value returned by the waitpid system call or equivalent function.  Exit statuses fall between 0 and 255, though, as explained below, the shell may use  values  above  125 specially. 
* Exit  statuses  from  shell builtins and compound commands are also limited to this range.  Under certain circumstances, the shell will use special values to indicate specific failure modes.
* For the shell's purposes, a command which exits with a zero exit status has succeeded.  An exit status of zero indicates  success.  A non-zero exit status indicates failure.  
* When a command terminates on a fatal signal N, bash uses the value of 128+N as the exit status.
* Important: Bash  itself returns the exit status of the last command executed, unless a syntax error occurs, in which case it exits with a non-zero value.  See also the exit builtin command below.
## Signals
* Section describes how bash behaves on reciving diffrent kind of signals
* When bash is interactive, in the absence of any traps, it ignores SIGTERM (so that kill 0  does  not  kill  an interactive  shell),  and  SIGINT  is  caught and handled (so that the wait builtin is interruptible).  In all cases, bash ignores SIGQUIT.  If job control is in effect, bash ignores SIGTTIN, SIGTTOU, and SIGTSTP.
## Job control
* Job control refers to the ability to selectively stop  (suspend)  the  execution  of  processes  and  continue(resume)  their  execution at a later point.  
* A user typically employs this facility via an interactive interface supplied jointly by the operating system kernel terminal driver and bash.
* The shell associates a job with each pipeline.  It keeps a table of currently executing  jobs,  which  may  be listed  with  the  jobs  command.  
* When bash starts a job asynchronously (in the background), it prints a linethat looks like: [1] 25647 indicating that this job is job number 1 and that the process ID of the last process in the  pipeline  associated  with  this  job  is 25647.
## Prompting
* When executing interactively, bash displays the primary prompt PS1 when it is ready to read a command, and the secondary prompt PS2 when it needs more input to complete a command.  
* Bash displays PS0 after it reads a  command  but  before  executing  it.
* In this section there is explanation how to customize PS1 and PS2
## Readline
* IMPORTAT: this section explains keyboard shortcuts, completion rules etc. 
* This is the library that handles reading input when using an interactive shell, unless the --noediting  option is  given  at  shell  invocation.  Line editing is also used when using the -e option to the read builtin.  
* By default, the line editing commands are similar to those of Emacs.  A vi-style line editing interface  is  also available.
## History
* When  the  -o  history option to the set builtin is enabled, the shell provides access to the command history, the list of commands previously typed.  
* The value of the HISTSIZE variable is used as the number  of  commands to  save  in a history list.  The text of the last HISTSIZE commands (default 500) is saved.
* On startup, the history is initialized from the file named by the variable HISTFILE (default ~/.bash_history).
* The builtin command fc (see SHELL BUILTIN COMMANDS below) may be used to list or edit and re-execute a portion of the history list.
## History expansion
* The  shell supports a history expansion feature that is similar to the history expansion in csh.  
* This section describes what syntax features are available.  This feature is enabled by default for interactive shells,  and can be disabled using the +H option to the set builtin command (see SHELL BUILTIN COMMANDS below).  
* Non-interactive shells do not perform history expansion by default.
## Shell builtin commands
* Section contains list of all builtin commands and their usage
## Restricted shell
* If  bash  is  started  with  the  name  rbash,  or  the -r option is supplied at invocation, the shell becomes restricted.  
* A restricted shell is used to set up an environment more controlled than the standard shell.
* It behaves identically to bash with the exception that the following are disallowed or not performed (e.g.):
	* changing directories with cd
	* setting or unsetting the values of SHELL, PATH, ENV, or BASH_ENV
	* specifying command names containing /
	* etc.
