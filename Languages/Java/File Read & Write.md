# Open file
```java
public FileWriter openDataFile() {
	//Creation of save-file if not exist
	try {
		File file = new File("KeyValueToolDataStoreFile.csv");
		if (file.createNewFile())
			System.out.println("Data file created");
		else
			System.out.println("Data file already created");
		}
		return new FileWriter(file, true); //Appends to current file
		return new FileWriter(file);//Overwrites current file
	}
	catch (IOException e){
		System.out.println("Error accessing data file");
	}
	return null;
}
```

# Read file
```java
public void readData() {
	String row;
	try {
		FileWriter dataFile = openDataFile();
		if (dataFile != null) {
			BufferedReader cvsReader = new BufferedReader(new FileReader("KeyValueToolDataStoreFile.csv"));
			while ((row = cvsReader.readLine()) != null) {
				System.out.println(row);//Output data
				//Do something with data - could add to hashmap like below, or whatever
				//String[] data = row.split(",");
				//keyValueStore.put(data[0], data[1]);
			}
			cvsReader.close();
		}
	}
	catch (IOException e){
		System.out.println("Unable to save data from datafile");
	}
}
```

# Add to file
```java
//Adds to file - this in particular adds to the file in a HashMap format.
public String addToFile(String key, String value) {
	try {
		dataFile.append(key);
		dataFile.append(",");
		dataFile.append(value);
		dataFile.append("\n");

		dataFile.flush();
	}
	catch(IOException e){
		System.out.println("Error saving to file");
	}
	return this.keyValueStore.put(key, value);
}
```

# Delete from file
```java
//Delete from the file - this removes the data from the datastructure in the code holding the data (Hashmap) then 
//copies from the datastructure to the file andoverwrites the file with all new data.  Notice the FileWriter open with a 'true' parameter.   
public String delete(String key){
	try {
	if(keyValueStore.remove(key) == null)
		return "That does not exist";

	FileWriter fileWriter = openDataFile();

	for(Map.Entry<String, String> set : keyValueStore.entrySet()){
		if(!set.getKey().equals(key)){
			fileWriter.append(set.getKey());
			fileWriter.append(",");
			fileWriter.append(set.getValue());
			fileWriter.append("\n");
			}
		}
	fileWriter.flush();
	fileWriter.close();
	}
	catch (IOException e){
		System.out.println("Couldn't delete item");
	}
	return "successful deletion";
}
```

# Best Practices
When writing files in Java, it is best practice to:
-   Use the try-with-resources statement to automatically handle file closing and to ensure that the file is closed even in case of an exception.
-   Catch specific exceptions such as IOException and handle them appropriately.
-   Use the FileWriter or PrintWriter class for character-based file writing and the FileOutputStream or BufferedOutputStream for byte-based file writing.

When reading files in Java, it is best practice to:
-   Use the BufferedReader class for improved performance when reading large files or reading from a file multiple times.
-   Catch specific exceptions such as FileNotFoundException or IOException and handle them appropriately.
-   Use the FileInputStream or BufferedInputStream for byte-based file reading and the FileReader for character-based file reading.
-   Always be sure to close the file after reading or writing to release the resources and avoid memory leaks.

## Example using a try-with-resources statement
The try-with-resources statement is used to automatically handle file closing, so you don't need to explicitly close the file
```java
public FileWriter openAndWriteFile() {
	try (FileWriter writer = new FileWriter("example.txt")) {
	    writer.write("Hello World!");
	} catch (IOException e) {
	    System.out.println("An error occurred while writing the file.");
	    e.printStackTrace();
	}
}
```