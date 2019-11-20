# Database Storage Structures
[Link to article](https://en.wikipedia.org/wiki/Database_storage_structures)  
Database tables and indexes may be stored on disk in one of a number of forms, including ordered/unordered flat files, ISAM, heap files, hash buckets, or B+ trees. Each form has its own particular advantages and disadvantages.  
The most commonly used forms are B+ trees and ISAM. Such forms or structures are one aspect of the overall schema used by a database engine to store information.  
## Unordered
* Unordered storage typically stores records in the order they are inserted. For example, a heap Unordered storage typically stores the records in the order they are inserted. 
* Such storage provides fast inserting: O(1), but slow retrieval O(n)
## Ordered
* Ordered storage typically stores the records in order and may have to rearrange or increase the file size when a new record is inserted, resulting in lower insertion efficiency. However, ordered storage provides more efficient retrieval as the records are pre-sorted O(logn)
## Structured files
* Heap files
	* Although sharing a similar name, heap files are widely different from in-memory heaps. 
	* In-memory heaps are ordered, as opposed to heap files
	* Simplest and most basic method
		* insert efficient, with new records added at the end of the file, providing chronological order
		* retrieval efficient when the handle to the memory is the address of the memory
		* search inefficient, as searching has to be linear
	* Advantages
		* efficient for bulk loading data
		* efficient for relatively small relations as indexing overheads are avoided
	* Disadvantages
		* not efficient for selective retrieval using key values, especially if large
		* sorting may be time-consuming
* Hash buckets a.k.a Hash Tables
	* Hash functions calculate the address of the page in which the record is to be stored based on one or more fields in the record
	* Advantages
		* efficient for exact matches on key field
		* hash functions ensure even spread of data
	* Disadvantages
		* not suitable for range retrieval, which requires sequential storage
		* calculates where the record is stored based on fields in the record
* B+ trees
	* These are the most commonly used in practice.
	* Time taken to access any record is the same because the same number of nodes is searched
	* Index is a full index so data file does not have to be ordered
	* Advantages
		* access is fast
		* versatile data structure – sequential as well as random access
		* supports exact, range, part key and pattern matches efficiently.
	* Disadvantages
		* less well suited to relatively stable files – in this case, ISAM is more efficient