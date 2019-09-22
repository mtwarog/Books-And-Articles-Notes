# Creating Custom Exception  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-new-custom-exception)  
**Purpose**: Main reasons to introduce new exceptions are: Business logic exceptions or to catch and provide specific treatment to a subset of existing Java exceptions.  
## Custom Checked Exceptions
* Checked exceptions are exceptions that need to be treated explicitly.
* To create a custom exception, we have to extend the java.lang.Exception class.
## Custom Unchecked Exception
* To create a custom unchecked exception we need to extend the java.lang.RuntimeException class