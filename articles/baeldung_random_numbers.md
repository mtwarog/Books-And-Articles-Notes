# Generating Random Numbers in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-generate-random-long-float-integer-double)
* Article shows how to generate random numbers using:
	* plain Java
	* Apache Commons Math library
## Generate an Unbounded Long
* long generatedLong = new Random().nextLong();
## Generate a Long within a Range
* plain Java
	* long generatedLong = leftLimit + (long) (Math.random() * (rightLimit - leftLimit));
* Apache Commons Math
	* long generatedLong = new RandomDataGenerator().nextLong(leftLimit, rightLimit);
## Generate an Unbounded Integer
* int generatedInteger = new Random().nextInt();
## Generate an Integer within a Range
* plain Java
	* int generatedInteger = leftLimit + (int) (new Random().nextFloat() * (rightLimit - leftLimit));
* Apache Commons Math
	* int generatedInteger = new RandomDataGenerator().nextInt(leftLimit, rightLimit);
## Generate an Unbounded Float
* analogous to above examples (no point in copying it here)
## Generate a Float within a Range
* analogous to above examples (no point in copying it here)
## Generate an Unbounded Double
* analogous to above examples (no point in copying it here)
## Generate a Double within a Range
* analogous to above examples (no point in copying it here)