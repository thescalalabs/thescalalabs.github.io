---
title: Scala Basics
date: 2016-10-16 09:02:21
description:  Learn the basics of programming with scala
---

## Declaring Values and Variables
There two ways of declaring things that hold information in scala. 1. A value declared with `val` and a variable declared with 2. `var`. A value is just a constant. Once defined it can not be changed. In other words, it is immutable. On the other hand, variable is like any other variable in other languages. It can be changed and is mutable.

``` scala
val languageName = "scala"
languageName = "scala 2.12" // compilation error
```
``` scala
var languageName = "scala"
languageName = "scala 2.12" // valid scala code
```

<div class="ui info message">
  In the above code snippet, the name of both are `languageName`. This is valid because, after the declaration of the immutable `languageName`, the mutable declaration hides it. This creates a new binding in the current scope for `languageName`.
</div>

In the first code snippet, reassigning `languageName` throws an error because `val` is immutable. Once assigned a value, it cannot be reassigned. In the second code snippet, reassignment is allowed because it is a `var`.

### Immutable vs Mutable

## Variable Types and Type Inference
Scala is a statically typed language. This means that each value has a type associated with it. The types should match in order for the program to compile successfully. Scala also has local type inference. This means that it can infer the types of values and variables most of the times without we mentioning it. This reduces the verbosity of the code.

In scala, the type is mentioned after the value and not before as in java. For example, in java, declaring an integer would be
``` java
int age = 27
```
where as in scala, it is
``` scala
val age : Int = 27
```

One important point to note is that it is an error to declare a value or a variable without initializing it. This gives rise to a question that how do we handle declaring values and initializing it inside the constructor of a class. Well scala has its own way of achieving this. Also separating the declaration and initialization are source of the dreaded `NullPointerExcpetion`. Writing idiomatic scala code means avoiding null pointer exceptions as much as possible. Scala does not prohibit you from writing code that is initialized with null like `val name : String = null`. It is the users responsibility to avoid null pointer exceptions in this case.

Also notice that there are no semicolons at the end. Semicolons are required only if there are multiple statements within a single line. In that case, each statement should be delimited by a semicolon.


Declaration of multiple values together is possible. But all of them will be initialized with the single value.

``` scala
> val length, breadth = 100
length: Int = 100
breadth: Int = 100
```
Trying to initialize multiple bindings with different values in the same line will cause a compilation error.
``` scala
> val length, breadth = 50, 20
<console>:1: error: ';' expected but ',' found.
val length, breadth = 100,20
                         ^
```
If you want to achieve the above, you can use the destructuring capabilities of scala with tuples like below:
``` scala
> val (length, breadth) = (50, 20)
length: Int = 50
breadth: Int = 20
```

## Commonly used types
