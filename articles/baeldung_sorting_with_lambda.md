# Comparison (Sorting) with Lambda in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-8-sort-lambda)  
* Basic Sort without Lambdas
	* Before Java 8, sorting a collection would involve creating an anonymous inner class for the Comparator
	* e.g. new Comparator<Human>() {@Override public int compare(...){...}}
* Basic Sorting with Lambdas
	* With the introduction of Lambdas, we can now bypass the anonymous inner class and achieve the same result with simple, functional semantics
	* e.g. (final Human h1, final Human h2) -> h1.getName().compareTo(h2.getName());
* Basic Sorting with Type Inference	
	* We can further simplify the expression by not specifying the type definitions – the compiler is capable of inferring these on its own:
	* (h1, h2) -> h1.getName().compareTo(h2.getName())
* Sort using Reference to Static Method
* Sort Extracted Comparators
	* We can also avoid defining even the comparison logic itself by using an instance method reference and the Comparator.comparing method – which extracts and creates a Comparable based on that function.
* Reverse Sort
	* JDK 8 has also introduced a helper method for reversing the comparator 
	* e.g. Comparator<Human> comparator = (h1, h2) -> h1.getName().compareTo(h2.getName()); humans.sort(comparator.reversed());
* Sort with Multiple Conditions
	* The comparison lambda expressions need not be this simple – we can write more complex expressions as well – for example sorting the entities first by name, and then by age
* Sort with Multiple Conditions - Composition
	* Starting with JDK 8, we can now chain together multiple comparators to build more complex comparison logic
	* e.g. humans.sort(Comparator.comparing(Human::getName).thenComparing(Human::getAge));
* Sorting a List with Stream.sorted()
	* We can also sort a collection using Java 8’s Stream sorted() API. 
	* We can sort the stream using natural ordering as well as ordering provided by a Comparator. For this, we have two overloaded variants of the sorted() API
		* sorted() – sorts the elements of a Stream using natural ordering; the element class must implement the Comparable interface.
		* sorted(Comparator<? super T> comparator) – sorts the elements based on a Comparator instance
* Sorting a List in Reverse with Stream.sorted()
	* We can also use Stream.sorted() to sort a collection in reverse.