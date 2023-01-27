# Return statement - optional
- **Last line** of methods are returned

# Types - optional
- **Untyped** variable, use Def:
	`Def date = new Date()`
	
- **Typed** variables and methods:
	-   Same as in Java

# Strings
-   Can use double or single quotes for wrapping
-   Strings over multiple lines, use triple quotes:
```groovy
Def s3 = """`
	A
	Multiple
	Line
	String
	Test
	"""
```

## String interpolation:
-   Add $ in front of variable:
```groovy
Println "x is $y"
```

## Code interpolation:
-   Add ${} between method - Only works with double quotes
```groovy
`Def myCourse = "gradle"`
`Println "I'm training in: ${myCourse.toUpperCase()}"`
```