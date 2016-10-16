---
title: scala-basics
date: 2016-10-16 09:02:21
---

Type parameters are concepts that lets you abstract a specific `class` / `function` over a range of types. In other words the classes and functions that has type parameters can work with instance of types that are within the limit of the specified type parameter. Type parameters in scala are similar to generics in Java. Default scala collections make heavy use of type parameters. This is because a collection by itself is an abstract entity and it can work with multiple types. `List` is one such collection. It can work with `Int`, `String` or even custom classes. `List` does not care about the entity inside the collection. Irrespective of the entity inside, it provides few operations like `map`, `filter` etc. Type parameters are usually written inside `[]` in scala where as in java, it is written inside `<>`. It is usually denoted by single letter upper case letters like `A`, `B`, `T` etc.

``` scala
val listOfIntegers : List[Int] = List(1,2,3)
val listOfString : List[String] = List("a","b","c")
```

In the above code, the `List` is the collection. As you can see, it is used with both `String` and `Int`. In the case of `listOfIntegers`, the list has been parameterized with  `Int` and in the case of `listOfString`, the list has been parameterized with `String`. The definition of list would look like the following:

```
case class List[A]()....
```

Here `A` is the type place holder for the type parameter. This shows that parameteried types can work with values of any types. There is one more method to accomplish storing of different values in a collection in Java. It is the `ArrayList` type that lives under `java.util` package. Let see an example of `ArrayList` in action below.

``` java
import java.util.*;
ArrayList stringArrayList = new ArrayList();
stringArrayList.add("a");
stringArrayList.add("b");
stringArrayList.add("c");
ArrayList numberArrayList = new ArrayList();
numberArrayList.add(1);
numberArrayList.add(2);
numberArrayList.add(3);
```

As you can see, the `stringArrayList` and `numberArrayList` can work both strings and ints. So what is the difference between this `ArrayList` in java and `List` in scala? Well an `ArrayList` instance can accept a value of any type. But a `List` of `Int` can accept only integers.

``` scala
stringArrayList.add(4); // this is valid in java
listOfString +: "a" // this is a compile time error in scala
```

What is the meaning of the above code snippet? It means that though `ArrayList` can accept value of any type, it cannot provide operations specific to the type it accepts. Thats because it accepts `Object` which is the super class of all classes in java. It can only provide operations that are possible on an `Object`. Where as, the scala `List` can accept values of any type, but it can accept values of only one type for a single instance of the list. This means, the `List` is aware of the type it takes in and hence can provide some additional type safety. We will see about this type safety in detail later.
