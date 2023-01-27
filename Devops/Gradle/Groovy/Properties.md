"**Properties are the collection of values in a class.**  A class can have multiple properties. For example, objects classified as computers have the following properties: Hardware ID, Manufacturer, Model, and Serial Number."

## Getters / Setters
-   Implemented behind the scenes - no need to write them.
-   Edit objects as you would with direct access, groovy automatically uses getters / setters.

## Hashmaps
-   You can create a hashmap using Map m = new HashMap()
-   You can assign key/value with `m.put ('foo", "fred")`

-   Groovy lets you use dot notation on the hashmaps:
```groovy
	m.foo = 'test'
	Println(m.foo)
```