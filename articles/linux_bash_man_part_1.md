# Bash MAN page - part I  
**Definition**: Bash  is  an sh-compatible command language interpreter that executes commands read from the standard input or from a file.  
Bash also incorporates useful features from the Korn and C shells (ksh and csh).  
**Bash and POSIX**: Bash is intended to be a conformant implementation of the Shell and Utilities portion of the IEEE POSIX specification (IEEE Standard 1003.1).  Bash can be configured to be POSIX-conformant by default.  
## Shell Grammar
* Simple Commands
	* A simple command is a sequence of optional variable assignments followed by blank-separated words and redirections,  and  terminated  by  a  control operator.  The first word specifies the command to be executed, and is passed as argument zero.  The remaining words are passed as arguments to the invoked command.
* Pipelines
	* A pipeline is a sequence of one or more commands separated by one of the control operators | or |&.
* Lists
	* A  list  is a sequence of one or more pipelines separated by one of the operators ;, &, &&, or ||, and optionally terminated by one of ;, &, or <newline>.
* Compound Commands
	* A  compound command is one of the following: (list), {list; }, ((expression)), [[ expression ]].  In most cases a list in a command's description may be separated from the rest of the command by one or more newlines, and may be followed by a newline in  place  of  a  semicolon.
* Coprocesses
	* A coprocess is a shell command preceded by the coproc reserved word.  A coprocess is  executed  asynchronously in  a  subshell, as if the command had been terminated with the & control operator, with a two-way pipe established between the executing shell and the coprocess.
* Shell Function Definitions
	*  A  shell function is an object that is called like a simple command and executes a compound command with a new set of positional parameters.
## Quoting
* Quoting  is  used  to  remove the special meaning of certain characters or words to the shell.  Quoting can be used to disable special treatment for special characters, to prevent reserved words from being  recognized  as such, and to prevent parameter expansion.
* There are 3 quoting mechanisms:
	* escape character - A non-quoted backslash (\) is the escape character.  It preserves the literal value of the next character that follows, with the exception of <newline>.
	* single quotes - Enclosing characters in single quotes preserves the literal value of each character within the quotes.  A single quote may not occur between single quotes, even when preceded by a backslash.
	* double quotes - Enclosing  characters  in  double quotes preserves the literal value of all characters within the quotes, with the exception of $, `, \, and, when history expansion is enabled, !.
## Parameters
* A  parameter  is  an  entity that stores values.  It can be a name, a number, or one of the special characters listed below under Special Parameters.  A variable is a parameter denoted by a name.  A variable has  a  value and  zero or more attributes.  Attributes are assigned using the declare builtin command.
* Special parameters
	* * expands to the positional parameters starting from one.
	* @ Expands  to  the  positional  parameters,  starting  from one.  When the expansion occurs within double quotes, each parameter expands to a separate word.  That is, "$@" is equivalent to "$1"  "$2"  ...
	* # Expands to the number of positional parameters in decimal.
	* ? Expands to the exit status of the most recently executed foreground pipeline.
	* $ Expands  to the process ID of the shell.
	* etc.
* Shell variables
	* e.g. BASH, BASHOPTS, BASH_ARGV, HOSTNAME etc.
## Arrays
* Bash provides one-dimensional indexed and associative array variables.  
	* Any variable may be used as an indexedarray;  the  declare  builtin  will  explicitly declare an array.  
	* There is no maximum limit on the size of an array, nor any requirement that members be indexed or assigned contiguously.  
* Indexed  arrays  are  referenced using  integers (including arithmetic expressions) and are zero-based; associative arrays are referenced using arbitrary strings.  Unless otherwise noted, indexed array indices must be non-negative integers.
## Expansion
* Expansion  is  performed  on  the  command  line after it has been split into words.  There are seven kinds of expansion performed: brace expansion, tilde expansion, parameter and variable expansion, command substitution, arithmetic expansion, word splitting, and pathname expansion.
* Brace Expansion
* Tilde Expansion
* Parameter Expansion
* Command Substitution
* Arithmetic Expansion
* Process Substitution
* Word Splitting
* Pathname Expansion
* Quote Removal
## Redirections
* Before a command is executed, its input and output may be redirected using a special notation  interpreted  by the  shell.
	* Redirection allows commands' file handles to be duplicated, opened, closed, made to refer to different files, and can change the files the command reads from and writes to.  
	* Redirection may also be used  to modify  file handles in the current shell execution environment.  
	* The following redirection operators may precede or appear anywhere within a simple command or may follow a command.
	* Redirections are  processed  in  the order they appear, from left to right.
* Redirecting Input
	* Redirection of input causes the file whose name results from the expansion of word to be opened for reading on file descriptor n, or the standard input (file descriptor 0) if n is not specified.
* Redirecting Output
	* Redirection of output causes the file whose name results from the expansion of word to be opened for  writing on  file descriptor n, or the standard output (file descriptor 1) if n is not specified.  If the file does not exist it is created; if it does exist it is truncated to zero size.
* Here Documents
	* This type of redirection instructs the shell to read input from the current source  until  a  line  containing only delimiter (with no trailing blanks) is seen.
* Here Strings
	* A variant of here documents, the format is: [n]<<<word
* Duplicating File Descriptors
	* The redirection operator [n]<&word is used to duplicate input file descriptors.
	* Similarly [n]>&word is used to duplicate output file descriptor
* Moving File Descriptors
	* Redirection [n]<&digit- moves the file descriptor digit to file descriptor n
* Opening File Descriptors for Reading and Writing
	* [n]<>word causes the file whose name is the expansion of word to be opened for both reading and writing on file descriptor n, or on file descriptor 0 if n is not specified.  If the file does not exist, it is created.
