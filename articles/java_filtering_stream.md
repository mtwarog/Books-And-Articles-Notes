# Filtering a Stream of Optionals in Java  
[Link to article](https://www.baeldung.com/java-filter-stream-of-optional)  
**Purpose**: To filter out non-empty values from Stream of Optionals.  
## Using filter()
* By using filter with Optional::isPresent and then perform mapping with the Optional::get to extract values
* e.g. List<String> filteredList = listOfOptionals.stream().filter(Optional::isPresent).map(Optional::get).collect(Collectors.toList());
## Using flatMap()
* By using flatMap with lambda expression that converts an empty Optional to an empty Stream instance and non-empty Optional to Stream instance containing one element
* e.g. List<String> filteredList = listOfOptionals.stream().flatMap(o -> o.isPresent() ? Stream.of(o.get()) : Stream.empty()).collect(Collectors.toList());
## Java 9's Optional::stream
* The same as with flatMap(), but using new method Optional::stream
* e.g. List<String> filteredList = listOfOptionals.stream().flatMap(Optional::stream).collect(Collectors.toList());

