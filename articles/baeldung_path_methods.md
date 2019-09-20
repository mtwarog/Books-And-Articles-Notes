## Comparing getPath(), getAbsolutePath(), getCanonicalPath() in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-path)  
**Purpose**: java.io.File class contains all 3 methods to obtain the filesystem path  
## getPath()
* This is essentially the pathname passed to the File constructor
* If the File object was created using a relative path, the returned value from getPath() method would also be a relative path.
* The returned String always uses the platform’s default name-separator character.
## getAbsolutePath()
* The pathname of the file after resolving the path for the current user directory
* eg. /home/username/baeldung/foo/foo-one.txt     // on Unix systems, C:\Users\username\baeldung\foo\foo-one.txt  // on Windows systems
## getCanonicalPath()
* goes a step further and resolves the absolute pathname as well as the shorthands or redundant names like “.” and “..“ as per the directory structure. It also resolves symbolic links on Unix systems and converts the drive letter to a standard case on Windows systems.
* e.g. /home/username/baeldung/bar/bar-one.txt     // on Unix systems, C:\Users\username\baeldung\bar\bar-one.txt  // on Windows systems