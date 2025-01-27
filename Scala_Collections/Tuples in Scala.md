
A **tuple** in Scala is an **ordered collection** of elements that can hold **heterogeneous (different types of) values**. Tuples are **immutable** and can have up to **22 elements**.

Creating Tuples

```scala
val tuple1 = (1, "Scala", 3.14) // Tuple of Int, String, and Double
println(tuple1) // Output: (1,Scala,3.14)
```

Accessing Tuple Elements

```scala
val tuple2 = ("John", 25, true)

println(tuple2._1) // Output: John
println(tuple2._2) // Output: 25
println(tuple2._3) // Output: true
```

Note: **Indexing starts from 1**, not 0.

Tuple Operations

```scala
val pair = ("Hello", 42)
val swapped = pair.swap
println(swapped) // Output: (42,Hello)
```

Nested Tuples

```scala
val nestedTuple = (1, ("Scala", 3.14), "Hello")
println(nestedTuple._2._1) // Output: Scala
```

## **Tuple vs List**

|Feature|Tuple|List|
|---|---|---|
|Fixed Size|✅ Yes|❌ No (dynamic)|
|Immutable|✅ Yes|✅ Yes|
|Heterogeneous|✅ Yes|❌ No (only same type)|
|Supports Indexing|✅ Yes (`_1, _2`)|✅ Yes (`list(0)`)|

### **When to Use Tuples?**

✔ Use **tuples** when you need to return **multiple values** from a function.  
✔ Use **tuples** when elements are **fixed in number and order**.  
✔ Use **case classes** if you need **descriptive field names** instead of `_1, _2, _3`.

---

program that creates a tuple from two lists.

```scala
val list1 = List("Red", "Green", "Blue") 
val list2 = List(1, 3, 5) 
// Create a tuple from the lists 
val new_tuple = list1.zip(list2)
```

---
# Check if a specific element exists in a tuple

```scala
val nums = (1, 2, 3, 4, 5) println("Tuple elements: "+nums) // Check if the tuple contains a specific element 
val elementToCheck = 3 
val containsElement = nums.productIterator.contains(elementToCheck)

// productIterator , iterate over tuple --> (1, 2, 3, 4, 5)
```

---

# Merge two tuples

```scala
val tuple1 = (10, "Scala")

val tuple2 = (15.5, true)

(tuple1._1, tuple1._2, tuple2._1, tuple2._2)
```

---

