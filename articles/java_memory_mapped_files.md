# Memory-mapped files in Java  
* Introduced in Java 4 (JDK 1.4)
* Utility for efficient file reading
## In general 
[Wiki](https://en.wikipedia.org/wiki/Memory-mapped_file)  
* Is a segment of virtual memory that has been assigned a direct byte-for-byte correlation with some portion of a file or file-like resource. This resource is typically a file that is physically present on disk, but can also be a device, shared memory object, or other resource that the operating system can reference through a file descriptor
* Benefits:
	* increasing I/O performance, specially with large files.
	* possible benefit of memory-mapped files is a "lazy loading", thus using small amounts of RAM even for a very large file. 
* Drawbacks:
	* The standard I/O approach is costly due to system call overhead and memory copying. The memory-mapped approach has its cost in minor page faults—when a block of data is loaded in page cache, but is not yet mapped into the process's virtual memory space.
	* Another drawback of memory-mapped files relates to a given architecture's address space: a file larger than the addressable space can have only portions mapped at a time, complicating reading it. 
## java.nio.MappedByteBuffer class
* https://www.baeldung.com/java-mapped-byte-buffer
	* Only part of the file can be loaded if file is too big for available memory
	* This is a very efficient way to read a content of the file multiple times, as the file is mapped into memory and subsequent reads do not need to go to disc every time.
## Support in other languages:
* The function mmap(),[6] which creates a mapping of a file given a file descriptor, starting location in the file, and a length, is part of the POSIX specification
* Boost C++
* Perl File:Map
* Python nmap
* Java FileChannel