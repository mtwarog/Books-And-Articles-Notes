# Bash MAN page - part I  
**Definition**: Bash  is  an sh-compatible command language interpreter that executes commands read from the standard input or from a file.  
## Aliases
* Aliases allow a string to be substituted for a word when it is used as the first word  of  a  simple  command.
	* The  shell  maintains  a list of aliases that may be set and unset with the alias and unalias builtin commands
* For almost every purpose, aliases are superseded by shell functions.
## Functions
* A shell function, defined as described above under SHELL GRAMMAR, stores a series of commands for later execution.  
* When the name of a shell function is used as a simple command name, the  list  of  commands  associated with  that  function  name  is  executed.
* Functions are executed in the context of the current shell; no new process is created to interpret them (contrast this with the execution of a shell script).
* When a function is executed,  the  arguments  to the function become the positional parameters during its execution.
* Functions  may  be recursive.  The FUNCNEST variable may be used to limit the depth of the function call stack and restrict the number of function invocations.  By default, no limit is imposed on the number  of  recursive calls.
## Arithmetic evaluation
* The  shell allows arithmetic expressions to be evaluated.  
* Evaluation is done in fixed-width integers  with  no check for overflow, though division by 0 is trapped and flagged as an error.  
* The operators and their precedence, associativity, and values are the same as in the C language.
* Shell variables are allowed as operands; parameter expansion is performed before the expression is  evaluated.
## Conditional expressions
* Conditional expressions are used by the [[ compound command and the test and [ builtin commands to  test  file attributes  and perform string and arithmetic comparisons.  Expressions are formed from the following unary or binary primaries.
* When  used  with  [[, the < and > operators sort lexicographically using the current locale. The test command sorts using ASCII ordering.
## Simple command expansion
* When a simple command is executed, the shell performs the following expansions, assignments, and redirections, from left to right:
	* The words that the parser has marked as variable assignments (those preceding  the  command  name)  and redirections are saved for later processing.
	* The  words  that  are not variable assignments or redirections are expanded.  If any words remain after expansion, the first word is taken to be the name of the command and the remaining words are the  arguments.
	* Redirections are performed as described above under REDIRECTION.
	* The  text  after the = in each variable assignment undergoes tilde expansion, parameter expansion, command substitution, arithmetic expansion, and quote removal before being assigned to the variable.
## Command execution
* This section describes what is the order of actions to execute command. A lot of if statements.
## Command execution environment
* The shell has an execution environment, which consists of the following:
	* open  files  inherited  by  the  shell  at invocation, as modified by redirections supplied to the exec builtin
	* current working directory as set by cd, pushd, popd or inherited by the shell at invocation
	* file creation mode mask as set by umask or inherited from shell parent
	* current traps set by trap
	* shell parameters that are set by variable assigment or with set or inherited
	* shell functions defined during execution or inherited 
	* options enabled at invocation or by set
	* options enabled by shopt
	* shell aliases defined with alias
	* various process IDs including those of background job, the value of $$ and the value of PPID
* When  a  simple  command other than a builtin or shell function is to be executed, it is invoked in a separate execution environment that consists of the following:
	* shell open files
	* current working directory
	* file creation mode mask
	* shell variables and functions marked for export
	* traps caught by the shell are reset to values inherited from shell's parent
