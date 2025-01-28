**Map** is a collection of key-value pairs. In other words, it is similar to dictionary. Keys are always unique while values need not be unique. Key-value pairs can have any data type. However, data type once used for any key and value must be consistent throughout. Maps are classified into two types: _mutable_ and _immutable_. By default Scala uses immutable Map. In order to use mutable Map, we must import **scala.collection.mutable.Map** class explicitly.

**Operations on a Scala Map**

There are three basic operations we can carry out on a Map:

1. **keys:** In Scala Map, This method returns an iterable containing each key in the map.
2. **values:** Value method returns an iterable containing each value in the Scala map.
3. **isEmpty:** This Scala map method returns true if the map is empty otherwise this returns false.


**Accessing Values Using Keys**

Values can be accessed using Map variable name and key.
If we try to access value associated with the key “John”, we will get an error because no such key is present in the Map. Therefore, it is recommended to use **contains()** function while accessing any value using key.  
This function checks for the key in the Map. If the key is present then it returns true, false otherwise.

----

**Updating the values**
If we try to update value of an immutable Map, Scala outputs an error. On the other hand, any changes made in value of any key in case of mutable Maps is accepted.

---

**Adding new key-value pair**

We can insert new key-value pairs in a mutable map using **+=** operator followed by new pairs to be added or updated.

**Deleting a key-value pair:**

Deleting a key-value pair is similar to adding a new entry. The difference is instead of **+=** we use **-=** operator followed by keys that are to be deleted.
