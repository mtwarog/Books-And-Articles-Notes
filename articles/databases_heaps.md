# Heaps in databases a.k.a Tables without Clustered Indexes  
[Link to article](https://docs.microsoft.com/en-us/sql/relational-databases/indexes/heaps-tables-without-clustered-indexes?view=sql-server-2017)  
* One or more nonclustered indexes can be created on tables stored as a heap
* When to use Heaps
	* 
* When not to use heaps
	* when the data is frequently returned in a sorted order
	* when the data is frequently grouped together
	* when ranges of data are frequently queried from the table
	* when there are no nonclustered indexes and the table is large. (In a heap, all rows of the heap must be read to find any row.)