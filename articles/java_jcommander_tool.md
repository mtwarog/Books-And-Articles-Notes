# jCommander (part of Java Roadmap)  
**Definition**: JCommander is a very small Java framework that makes it trivial to parse command line parameters.  
[Documentation](http://jcommander.org/)  
 You annotate fields with descriptions of your options and then ask JCommander to parse:  
 e.g. @Parameter(names = { "-log", "-verbose" }, description = "Level of verbosity") private Integer verbose = 1;  
 e.g. class Main {  
	@Parameter(names={"--length", "-l"})  
 	int length;  
	@Parameter(names={"--pattern", "-p"})  
	int pattern;  
	public static void main(String ... argv) {  
		Main main = new Main();  
 		JCommander.newBuilder()  
			.addObject(main)  
			.build()  
			.parse(argv);  
		main.run();  
	}  
	public void run() {  
		System.out.printf("%d %d", length, pattern);  
	}  
}  