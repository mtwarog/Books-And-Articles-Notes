# Database index  
**Definition**: Is a data structure that improves the speed of data retrieval operations on a database table at the cost of additional writes and storage space to maintain the index data structure.  
**Purpose**: Indexes are used to quickly locate data without having to search every row in a database table every time a database table is accessed.  
* An index is a copy of selected columns of data from a table that can be searched very efficiently that also includes a low-level disk block address or direct link to the complete row of data it was copied from
* Simply speaking, index in DB is the same as index in book. It is a map of selected terms from given content(row in DB) to specific places (pages in book, places in files in DB)
## Usage:
* Support for fast lookup
* Policing the database constraints
## Index architecture / Indexing methods
* Non-clustered
	* The data is present in arbitrary order, but the logical ordering is specified by the index.
	* The data rows may be spread throughout the table regardless of the value of the indexed column or expression. 
	* The non-clustered index tree contains the index keys in sorted order, with the leaf level of the index containing the pointer to the record (page and the row number in the data page in page-organized engines; row offset in file-organized engines).
	* There can be more than one non-clustered index on a database table.
* Clustered
	* Clustering alters the data block into a certain distinct order to match the index, resulting in the row data being stored in order. 
	* There can only be one such index, as it modifies data location for it's needs
	* Clustered indices can greatly increase overall speed of retrieval, but usually only where the data is accessed sequentially in the same or reverse order of the clustered index, or when a range of items is selected.
* Cluster
	* When multiple databases and multiple tables are joined, it's referred to as a cluster (not to be confused with clustered index described above)
	* The records for the tables sharing the value of a cluster key shall be stored together in the same or nearby data blocks. This may improve the joins of these tables on the cluster key, since the matching records are stored together and less I/O is required to locate them
## Types of Indexes:
* Bitmap index - indexing that stores the bulk of its data as bit arrays (bitmaps) and answers most queries by performing bitwise logical operations on these bitmaps. The most commonly used indexes, such as B+ trees, are most efficient if the values they index do not repeat or repeat a small number of times. In contrast, the bitmap index is designed for cases where the values of a variable repeat very frequently.
* Dense index - is a file with pairs of keys and pointers for every record in the data file. Every key in this file is associated with a particular pointer to a record in the sorted data file. 
* Sparse index -  is a file with pairs of keys and pointers for every block in the data file. Every key in this file is associated with a particular pointer to the block in the sorted data file.
* Reverse index - A reverse-key index reverses the key value before entering it in the index. E.g., the value 24538 becomes 83542 in the index. Reversing the key value is particularly useful for indexing data such as sequence numbers, where new key values monotonically increase.
* Primary index - The primary index contains the key fields of the table and a pointer to the non-key fields of the table. The primary index is created automatically when the table is created in the database. When you create the file, you must specify two things about the primary index: 1. The name of the primary index 2. The primary index specification
* Secondary index - It is used to index field that are neither ordering fields nor key fields (there is no assurance that the file is organized on key field or primary key field). One index entry for every tuple in the data file (dense index) contains the value of the indexed attribute and pointer to the block/record.
## Misc
* Heaps in databases a.k.a Tables without Clustered Indexes