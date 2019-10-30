# Hard vs symbolic(soft) link (Linux OS)    
[Link to article](https://shapeshed.com/unix-ln/#what-is-the-difference-between-a-hard-and-symbolic-link)  
* HARD LINK -> DATA ON DISC (one data can have many hard links)
* SYMBOLIC LINK -> HARD LINK -> DATA ON DISC (symbolic links points to hard links which point to data. If hard link is deleted, symbolic link stops working)
* Most of OSes disallows hard links to directories
* To create a hard link using the ln command pass the full path of the target file and the link name. This has the effect of creating a new file that links to the same data on disk as the target file.
	* e.g. ln target.txt link.txt (link.txt will point to the same data as target.txt)
* To create a symbolic link pass the -s option to the ln command followed by the target file and the name of link.
	* e.g. ln -s ~/code/notes/notes ~/bin/notes