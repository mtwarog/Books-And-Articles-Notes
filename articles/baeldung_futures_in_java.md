# Future (a.k.a CompletableFuture) in Java  
[Link to article](https://www.baeldung.com/java-future)  
**Purpose**: To have a container for value which will be yet computed by some other process.  
* Promise is quite similar, but promise value can be set by current process, as Future must be set by something external.
* Simply put, the Future class represents a future result of an asynchronous computation – a result that will eventually appear in the Future after the processing is complete.
* Introduced by Java 5
## Creating Futures
* Once we have an ExecutorService object, we just need to call submit() passing our Callable as an argument. submit() will take care of starting the task and return a FutureTask object, which is an implementation of the Future interface.
## Consuming Futures
* Future.isDone() tells us if the executor has finished processing the task. If the task is completed, it will return true otherwise, it returns false.
* The method that returns the actual result from the calculation is Future.get(). Notice that this method blocks the execution until the task is complete
* Suppose we’ve triggered a task but, for some reason, we don’t care about the result anymore. We can use Future.cancel(boolean) to tell the executor to stop the operation and interrupt its underlying thread
## More Multithreading with Thread Pools
* Creating different ThreadExecutors we can control number of threads running in parallel
	* Executors.newSingleThreadExecutor() - only one thread at any specific time
	* Executors.newFixedThreadPool() - fixed number of threads
	* Executors.newCachedThreadPool() - reuses previously used Threads when they are available
	* Executors.newScheduledThreadPool() - schedules commands to run after a given delay.
	* Read more: https://www.baeldung.com/java-executor-service-tutorial
## Overview of ForkJoinTask
* ForkJoinTask is an abstract class which implements Future and is capable of running a large number of tasks hosted by a small number of actual threads in ForkJoinPool.
* Read more: https://www.baeldung.com/java-fork-join
## Good Stack Explanation
[Link to Stack](https://stackoverflow.com/a/28821051/6708274)  
* "You can make a Promise and it's up to you to keep it. When someone else makes you a promise you must wait to see if they honour it in the Future"
* Futures and promises are pretty similar concepts, the difference is that a future is a read-only container for a result that does not yet exist, while a promise can be written (normally only once). The Java 8 CompletableFuture and the Guava SettableFuture can be thought of as promises, because their value can be set ("completed"), but they also implement the Future interface, therefore there is no difference for the client.
* The result of the future will be set by "someone else" - by the result of an asynchronous computation. Note how FutureTask - a classic future - must be initialized with a Callable or Runnable, there is no no-argument constructor, and both Future and FutureTask are read-only from the outside (the set methods of FutureTask are protected). The value will be set to the result of the computation from the inside.