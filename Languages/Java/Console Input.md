# Best Practice
The best practice for retrieving user input from the console in Java is to use the `Scanner` class, which is part of the standard Java library. This class allows you to easily read input from the console, including strings, integers, and other data types.

## Read a String
```java
Scanner scanner = new Scanner(System.in);
System.out.print("Enter a string: ");
String input = scanner.nextLine();
```
## Read an Int
```java
Scanner scanner = new Scanner(System.in);
System.out.print("Enter an integer: ");
int input = scanner.nextInt();
```

# Example
```java
public static void inputFromConsole() {
	//Variable declarations
	KeyValueTool kvt = new KeyValueTool();
	Scanner scanner = new Scanner(System.in);
	String stringInput;

	//Start of application
	System.out.println("Please enter a command.  Valid commands are: put, fetch, push, pop, delete, exit");
	System.out.print("> ");

	//Loop for user input
	try {
	while(scanner.hasNextLine()) {
		stringInput = scanner.nextLine().trim();
		if (stringInput.equals("exit")){
			System.out.println("Bye");
			break;
		}
		//Run chooseCommand function
		System.out.println(kvt.chooseCommand(stringInput)); //Make a command function
		System.out.print("> ");
	}
	}
	scaner.close()
}
```
