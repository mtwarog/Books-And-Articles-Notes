# Java Stacktrace to String 
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-stacktrace-to-string)  
**Purpose**: Sometimes we would like to write a stacktrace to file or transmit it over network.  
## Conversion with Core Java
* The function printStackTrace() of the Exception class can take one parameter, either a PrintStream or a PrintWriter. Thus, it is possible, using a StringWriter, to print the stack trace into a String
	* Then calling sw.toString() will return the stack trace as a String
## Conversion with Apache Commons-Lang
* Allows to simply use ExceptionUtils:
	* String stacktrace = ExceptionUtils.getStackTrace(e);