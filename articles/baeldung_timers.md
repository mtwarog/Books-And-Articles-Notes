# Java Timer  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-timer-and-timertask)  
## Timer - the Basics
* Timer and TimerTask are java util classes used to schedule tasks in a background thread. In a few words – TimerTask is the task to perform and Timer is the scheduler.
## Schedule a Task Once
* running a single task 
* e.g. TimerTask task = new TimerTask(){...}; Timer timer = new Timer("Timer"); timer.schedule(task, delay); // delay is a Long e.g. 1000L
## Schedule a Repeated Task at an Interval
* schedule a task to run at a pre-defined interval.
* e.g. timer.scheduleAtFixedRate(repeatedTask, delay, period);
*  if an execution is delayed for any reason (such as garbage collection or other background activity), two or more executions will occur in rapid succession to "catch up"
## Cancel Timer and TimerTask
* By calling cancel on timer e.g. timer.cancel(); 
## Timer vs ExecutorService
* You can also make good use of an ExecutorService to schedule timer tasks, instead of using the timer
* e.g. ScheduledExecutorService executor = Executors.newSingleThreadScheduledExecutor(); executor.scheduleAtFixedRate(repeatedTask, delay, period, TimeUnit.MILLISECONDS); Thread.sleep(delay + period * 3); executor.shutdown();
* main differences:
	* Timer can be sensitive to changes in the system clock; ScheduledThreadPoolExecutor is not
	* Timer has only one execution thread; ScheduledThreadPoolExecutor can be configured with any number of threads
	* Runtime Exceptions thrown inside the TimerTask kill the thread, so following scheduled tasks won’t run further; with ScheduledThreadExecutor – the current task will be canceled, but the rest will continue to run
* Quartz library 
	* big library for scheduling tasks in Java application