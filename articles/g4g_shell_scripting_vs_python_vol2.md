# Shell Scripting vs Python (pros and cons) 
[Link to article](https://opensource.com/article/19/4/bash-vs-python)  
## Bash
* Is a Linux/Unix shell command language
* Is great for writing shell scripts that use command line interface (CLI) utilities, utilizing output from one command to another (piping), and executing simple tasks (up to 100 lines of code)
* Can utilize command-line commands and utilities as-is
* Has better startup time than Python but poor execution time performance
* Does not come preinstalled in Windows; your script might not be compatible with multiple operating systems, but Bash is the default shell on most Linux/Unix systems
* Is not fully compatible with other shells (e.g., csh, zsh, fish)
* Piping ("|") CLI utilities like sed, awk, grep, etc. can slow its performance
* Lacks many functions, objects, data structures, and multi-threading, which limits its use for complex scripting/programming
* Lacks good debugging tools and utilities
## Python
* Is an object-oriented programming (OOP) language, so it's more general purpose than Bash
* Can be used for almost any task
* Works on most major operating systems and is also installed by default on most Unix/Linux systems
* Is very similar to writing pseudo code
* Has simple, clear, easy-to-learn, and easy-to-read syntax
* Has lots of libraries, documentation, and an active community
* Provides better error handling features than Bash
* Has better debugging tools and utilities than Bash, which makes it a great language for developing complex software applications involving many lines of code
* Applications (or scripts) can contain many third-party dependencies that must be installed before executing them
* Requires writing more lines of code f