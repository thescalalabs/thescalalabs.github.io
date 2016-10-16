---
title: Getting Started with Scala
date: 2016-10-16 09:02:21
description:  Get your environment up and running with scala
---
There are multiple ways to start working with scala. Each way has its own advantages. We will see two of those ways to getting started with scala. 1. REPL & 2. Integrated Development Environemt

### Read Eval Print Loop
This is just a shell program that accepts valid scala code, evaluates it, prints the result and wait for input again. In order to install scala use `brew install scala`. This will download the scala binary and installs in your system. Once the installation is done, typing `scala` in the terminal starts the scala REPL.

```
Welcome to Scala 2.11.8 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_101).
Type in expressions for evaluation. Or try :help.

scala>
```

Start entering scala code in it and it evaluates the result immediately.
``` scala
scala> val name = "scala"
name: String = scala
```
As you can see, the repl prints the result of evaluation immediately. Here it says that `name` has type of `String` and has the value `scala`. Note that the type of `name` is mentioned after it and not before it as we see in java. In java it could have been `String name = scala`.

Using a REPL has its own advantages and disadvantages. For example, you can quickly prototype short code snippets and see the result immediately. Press `up` to cycle through the previously entered commands. But once the number of lines of code increases, typing in a reply and editing the code becomes cumbersome. This is aleviated to some extent by using a repl command `:paste`. Here you can paste multiline code snippets and edit. But still, beyond simple use cases, using a REPL becomes painful.

A special mention here to the ammonite repl which reduces lots of pain points working with a repl.

### Integrated Development Environment
The most popular IDE for scala out there is Intellij Idea. Download Intellij Idea from [here](https://www.jetbrains.com/idea/download/) and install. Then install the scala plugin. Once it is installed, create a new scala project.
