# Cygwin vs MinGW  
[Stack answer](https://stackoverflow.com/questions/771756/what-is-the-difference-between-cygwin-and-mingw)  
## Simple answer
* Compile something in Cygwin and you are compiling it for Cygwin.
* Compile something in MinGW and you are compiling it for Windows.
## CygWin
* The purpose of Cygwin is to make porting Unix-based applications to Windows much easier, by emulating many of the small details that Unix-based operating systems provide, and are documented by the POSIX standards.
*  Your application can use Unix feature such as pipes, Unix-style file and directory access, and so forth, and it can be compiled with Cygwin which will act as a compatibility layer around your application, so that many of those Unix-specific paradigms can continue to be used.
## MinGW
* MinGW aims to simply be a Windows port of the GNU compiler tools, such as GCC, Make, Bash, and so on. It does not attempt to emulate or provide comprehensive compatibility with Unix, but instead it provides the minimum necessary environment to use GCC (the GNU compiler) and a small number of other tools on Windows.
* By default, code compiled in MinGW's GCC will compile to a native Windows X86 target, including .exe and .dll files, though you could also cross-compile with the right settings, since you are basically using the GNU compiler tools suite
## Misc
* For non-trivial software applications, making them cross-platform can be a considerable challenge unless you use a comprehensive cross-platform framework. At the time I wrote this the Qt framework was one of the most popular for this purpose, allowing the building of graphical applications that work across operating systems including Windows, but there are other options too.