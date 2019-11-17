# Shell Scripting vs Python (pros and cons) 
[Link to article](https://stackoverflow.com/questions/796319/strengths-of-shell-scripting-compared-to-python)  
## Some differences
* Shell scripting has simpler notations for I/O redirection.
* It is simpler to create pipelines out of existing programs in shell.
* Shell scripting reuses entire programs.
* Shell is universally available (on anything like Unix) - Python is not necessarily installed.
* The shell is not indispensable. Why do you think there are so many? bash, tcsh, csh, sh, etc., etc.,
* Python is a shell. Not the one you'd use for running all commands, but for scripting, it's ideal.
* Python is a more-or-less standard part of all Linux distro's.
* The more traditional shells do too many things.
## Conclusion:
* You need both
* You should never write a script with if-statements or loops in a traditional shell language.
* The shell makes common and simple actions really simple, at the expense of making more complex things much much more complex.