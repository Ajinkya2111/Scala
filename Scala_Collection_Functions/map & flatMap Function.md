
## Introduction

The functional combinators _map__()_ and _flatMap()_ are higher-order functions found on [_RDD_, _DataFrame_, and _DataSet_ in Apache Spark](https://www.baeldung.com/java-spark-dataframe-dataset-rdd). With these collections, we can perform transformations on every element in a collection and return a new collection containing the result.

## Example of _map()_

The _map()_ method transforms a collection by applying a function to each element of that collection. It then returns a new collection containing the result.

we’ll use _map()_ to split each string in the collection by the empty string:

```scala
val rdd = sc.parallelize(Seq("map vs flatMap", "apache spark"))
rdd.map(_.split(" ")).collect

res1: Array[String] = Array(Array("map", "vs", "flatMap"), Array("apache", "spark"))
```

**_map()_ transforms a collection of length N into another collection of length N**.



-------
## Example of _flatMap()_

flatMap()_ combines _mapping_ and _flattening_. It first runs the _map()_ method and then the _flatten()_
method to generate the result. The _flatten_ method **will collapse the elements of a collection to create a single collection with elements of the same type**.

```scala
val rdd = sc.parallelize(Seq("map vs flatMap", "apache spark"))
rdd.flatMap(_.split(" ")).collect

res1: Array[String] = Array("map", "vs", "flatMap", "apache", "spark")
```

_flatMap()_ runs _flatten()_ on this output, generating a new result that doesn’t contain nested collections but contains each element of the nested collection instead.

The **flatMap** function is applicable to both Scala's Mutable and Immutable data structures.

The **flatMap** method takes a predicate function, applies it to every element in the collection. It then returns a new collection by using the elements returned by the predicate function. The **flatMap** method is essentially a combination of the **map** method being run first followed by the **flatten** method.

```scala
def flatMap[B](f: (A) ⇒ GenTraversableOnce[B]): TraversableOnce[B]
```

The **flatMap** method is a member of the [TraversableLike](http://www.scala-lang.org/api/current/scala/collection/TraversableLike.html) trait but there are specialized versions of the **flatMap** methods for given collection types

GenTraversableOnce[B] is a predicate or condition to be applied on each element of the collection. This method returns the Option element containing the matched element of iterator which satisfiles the given condition.


```scala
object Demo {
   def main(args: Array[String]) = {
      val list = List(1, 5, 10)
      //apply operation
      val result = list.flatMap{x => List(x,x+1)}
      //print result
      println(result)      // List(1, 2, 5, 6, 10, 11)
   }
}
```


# Flatten Method

flatten() method is a member GenericTraversableTemplate trait, it returns a single collection of elements by merging child collections.

```scala
def flatten[B]: Traversable[B]
```

same like FlatMap method

```scala
object Demo {
   def main(args: Array[String]) = {
      val list = List(List(1,2), List(3,4))
      //apply operation
      val result = list.flatten
      //print result
      println(result)      // List(1, 2, 3, 4)
   }
}
```


**flatMap() combines mapping and flattening**. It first runs the map() method and then the flatten() method to generate the result. The flatten method will collapse the elements of a collection to create a single collection with elements of the same type.


Another useful way to use _flatMap_() is when dealing with a collection of type _Option_. Flattening the output allows us to quickly retrieve all the elements that have a value:
```scala
val mapOutput = strings.map(toInt)
mapOutput: Seq[Option[Int]] = List(Some(3), Some(5), None, Some(8), None, None, Some(12))

val flattenOutput = mapOutput.flatten
flattenOutput: Seq[Int] = List(3, 5, 8, 12)
```


