# Template Metaprogramming  
## Definition
* Metaprogramming technique in which templates are used by a compiler to generate temporary source code, which is merged by the compiler with the rest of the source code and then compiled.
## Usages
* Compile-time class generation
* Compile-time code optimization
* Static Polymorphism
* Read: "Barton-Nackman trick" on wiki
## Benefits and drawbacks
* Compile-time versus execution-time tradeoff 
	* If a great deal of template metaprogramming is used, compilation may become slow;
* Generic Programming
	* Template metaprogramming allows the programmer to focus on architecture and delegate to the compiler the generation of any implementation required by client code. Thus, template metaprogramming can accomplish truly generic code, facilitating code minimization and better maintainability
* Readability
	* "With respect to C++, the syntax and idioms of template metaprogramming are esoteric compared to conventional C++ programming, and template metaprograms can be very difficult to understand."
## History of Template Metaprogramming
* https://en.wikibooks.org/wiki/C%2B%2B_Programming/Templates/Template_Meta-Programming#History_of_TMP
* "Historically TMP is something of an accident; it was discovered during the process of standardizing the C++ language that its template system happens to be Turing-complete, i.e., capable in principle of computing anything that is computable."