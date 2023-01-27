Python files are called modules and they are identified by the `.py`  file extension. A module can define functions, classes, and variables.

Every Python Module (file) has a variable called **name**. This is set to **main** when the file is ran directly, OR it is set to the filename if the file is imported on another python file.

Hence, people typically use this if statement as a starting point for python code:

```bash
if __name__ == "__main__":
   #do things
else:
   #this would be ran if this code was included on an imported file
```