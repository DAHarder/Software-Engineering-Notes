# Notes:
The built-in data structures are also non-primitive data types.
-   Primitive types are predefined (already defined) in Java. Non-primitive types are created by the programmer and is not defined by Java (except for String).
-   Non-primitive types can be used to call methods to perform certain operations, while primitive types cannot.
-   A primitive type has always a value, while non-primitive types can be null.
-   A primitive type starts with a lowercase letter, while non-primitive types starts with an uppercase letter.
-   The size of a primitive type depends on the data type, while non-primitive types have all the same size.

# Primitive Data Types
| Data Type | Size    | Description                                                                       |
|-----------|---------|-----------------------------------------------------------------------------------|
| byte      | 1 byte  | Stores whole numbers from -128 to 127                                             |
| short     | 2 bytes | Stores whole numbers from -32,768 to 32,767                                       |
| int       | 4 bytes | Stores whole numbers from -2,147,483,648 to 2,147,483,647                         |
| long      | 8 bytes | Stores whole numbers from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| float     | 4 bytes | Stores fractional numbers. Sufficient for storing 6 to 7 decimal digits           |
| double    | 8 bytes | Stores fractional numbers. Sufficient for storing 15 decimal digits               |
| boolean   | 1 bit   | Stores true or false values                                                       |
| char      | 2 bytes | Stores a single character/letter or ASCII values                                  |

# Non-primitive Data Types 
(Non-primitive data types are called reference types because they refer to objects.)

-   Class
-   Object
-   String
-   Interface
-   Array

A [Class](https://www.javatpoint.com/object-and-class-in-java) in Java is a user defined data type i.e. it is created by the user. It acts a template to the data which consists of member variables and methods.

An [Object](https://www.javatpoint.com/object-and-class-in-java) is the variable of the class, which can access the elements of class i.e. methods and variables.

A **String** represents a sequence of characters for example "Javapoint", "Hello world", etc. String is the class of Java.

An [Interface](https://www.javatpoint.com/interface-in-java) is similar to a class however the only difference is that its methods are abstract by default i.e. they do not have body. An interface has only the final variables and method declarations. It is also called a fully abstract class.

An [Array](https://www.javatpoint.com/array-in-java) is a data type which can store multiple homogenous variables i.e., variables of same type in a sequence. They are stored in an indexed manner starting with index 0. The variables can be either primitive or non-primitive data types.

# Data Structures
## Array
---
### Create

### Add

### Remove

### Retrieve


## List
---
### Create:
```java
List<String> name = new ArrayList<>();
```
### Add:
``` java
name.add("Lion");
name.add(2,"Elephant"); //add at index
```
### Remove:
``` java
programmingLanguages.remove(5); //remove at index
boolean isRemoved = programmingLanguages.remove("Kotlin"); //remove first item that matches string.  Returns a boolean	```
```
### Retreive:
``` java
String bestCompany = topCompanies.get(0); //retreive via index
```

## Map
---
### Create:
```java
Map<String,Integer> mapName = new HashMap<>();
```
### Add:
```java
numberMapping.put("One",1); //adding with overwrite existing keys
numberMapping.putIfAbsent("Four",4); //add only if key doesn't exist
```
### Remove:
```java
mapName.remove("key"); // removes key from map, returns value associated with key or null if none
mapName.remove("key","value"); // removed key only if the value matches the key. Returns a boolean
```
### Retreive:
```java
if(mapName.containsKey("value")){ //check for existing key
if(mapName.containsValue("value")){ //check for existing value
String city = mapName.get("value"); //retrieve value to key - returns NULL if no key 
```

## Set
---
### Create:
```java
Set<String> setName = new HashSet<>(); //can add another collection object in the () to add all items to set
```
### Add:
```java
setName.add("One"); //adding duplicate keys will be ignored
```
### Remove:
```java
numbers.remove(item); // returns boolean
numbers.removeAll(ListItem); // removes all items within the list object (like arrayList)
numbers.removeIf(num -> num % 2==0); //removed based on condition
```
### Retreive:
```java
if(setName.contains(item)){ //check for existing key
```

## Linked List
---
### Create: 
```java
LinkedList<String> name = new LinkedList<>();
```
### Add: (O1) to all adds
```java
name.add("item"); //add item to end
name.addFirst("item") //add to front
name.addLast("item") // add to end
friends.add(3,"Lisa"); // at at index
```
### Remove:
```java
String firstElement = name.removeFirst(); //removes first item O(1)
String firstElement = name.removeLast(); //removes last item O(N)
String firstElement = name.remove("item"); //removes first item that matches string O(N)
```
### Retreive:
```java
String firstElement = name.getFirst(); //first item O(1)
String lastElement = name.getLast(); //get last item O(N)
String elementAtIndex = name.get(2);// get item at index O(N)
```

## Stack
---
### Create:
```java
Stack<String>stackOfCards = new Stack<>();
```
### Add:
```
stackOfCards.push("Jack");
```
### Remove:
```
N/A
```
### Retreive:
```java
stackOfCards.pop();// Throws EmptyStackException if the stack is empty
stackOfCards.peek(); // look at next item
int position = stackOfCards.search("Queen"); //returns 1-based position of item.  Returns -1 if not found
```

## Queue
---
### Create:
```java
Queue<String>waitingQueue = new LinkedList<>(); // Create and initialize a Queue using a LinkedList
```
### Add:
```java
waitingQueue.add("Rajeev");
```
### Remove:
```
N/A
```
### Retreive:
```java
name = waitingQueue.poll(); // returns and removes next item, or throws NoSuchElementException if the Queue is empty
waitingQueue.peek(); //returns next item without removing it
```

## Priority Queue
---
### Create:
```java
PriorityQueue<Integer>numbers = new PriorityQueue<>(); //implemented using LinkedList
```
### Add:
```java
numbers.add(750);
```
### Remove:
```
N/A
```
### Retreive:
```java
numbers.remove() // retrieves the item based on priority (lowest number first or alphabetical string)
```

## Binary Tree
---
### Create:

### Add:

### Remove:

### Retreive: