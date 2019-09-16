# Period and Duration classes in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-period-duration)
**Purpose**: Period and Duration are new classes for working with time introduced in Java 8. Both classes can be used to determine the distance in time between two dates.
The main distinction between the two classes is that Period uses date-based values, while Duration uses time-based values
## Period Class
* The Period class uses the units year, month and day to represent a period of time.
* e.g. Period period = Period.between(startDate, endDate);
* Then, we can determine the date units of the period using the methods getYears(), getMonths(), getDays()
* Period object can also be created by parsing a text sequence like "PnYnMnD"
## Duration Class
* The Duration class represents an interval of time in seconds or nanoseconds and is most suited for handling shorter amounts of time, in cases that require more precision
* e.g. Duration duration = Duration.between(start, end);
* Then we can use the getSeconds() or getNanoseconds() methods to determine the value of the time units
* A duration can be converted to other time units using toDays(), toHours(), toMillis(), toMinutes()