# Log Frameworks (part of Java Roadmap)  
Log4J descendants especially (log4j 2 and Logback)  
[Link to article](https://www.baeldung.com/java-logging-intro)  
## Why to log?
* Logging is a powerful aid for understanding and debugging program’s run-time behavior. Logs capture and persist the important data and make it available for analysis at any point in time.
## Enabling Logging
* All the logging frameworks discussed in the article share the notion of loggers, appenders (objects adding logs to different places like sockets, files etc.) and layouts (determines how message should look like).
* Enabling logging consists of 3 steps:
	* Adding needed libraries
	* Configuration
	* Placing log statements
## Log4j 2
* Log4j 2 is new and improved version of the Log4j logging framework. The most compelling improvement is the possibility of asynchronous logging.
* Configuration
	* Configuring Log4j 2 is based on the main configuration log4j.xml file. The first thing to configure is the appender.
	* These determine where the log message will be routed. Destination can be a console, a file, socket, etc.
* Logging to File
* Asnychronous Logging
* Usage
* Package Level Configuration
	* Logging level can be set independently for each package (e.g. for one dependency it can be DEBUG and for other INFO)
## Logback
* Logback is meant to be an improved version of Log4j, developed by the same developer who made Log4j.
* Logback also has a lot more features compared to Log4j, with many of them being introduced into Log4j 2 as well
* Logback uses SLF4J as an interface, so you need to import SLF4J’s Logger and LoggerFactory.
* SLF4J
	* SLF4J provides a common interface and abstraction for most of the Java logging frameworks. It acts as a facade and provides standardized API for accessing the underlying features of the logging framework.
## Log4j 
* Outdated but is a foundation for its successors.