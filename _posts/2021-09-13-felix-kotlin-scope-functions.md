---
layout: post
title: Kotlin scope functions
image: 2021-09-13-felix-kotlin-scope-functions.jpg
date: 2021-09-13
type: post
published: true
status: publish
category: Kotlin
tags: [programing]
author:
  login: pmhfelix
  email: 
  display_name: Pedro Félix
  image: felix.jpg
  role: Software Developer
  
---

[Kotlin scope functions](https://kotlinlang.org/docs/scope-functions.html) allow the execution of code blocks in a _richer_ scope, typically with the end goal of making code simpler to write and read.

There are five different scope functions: `let`, `also`, `with`, `apply`, and `run`.
They all receive an object and a code block that will have access to that object.

The `with` function is the only one that receives the object as a regular parameter.
That leaves us with four remaining functions, which can be neatly organized in a two by two table, according to the two differentiating aspects:

- How is the object made available to the block - via `this` or via the lambda’s parameter.

- What is the scope function’s evaluation result - the received object or the block’s evaluation result.

<img src="/assets/blog/2021-09-13-felix-kotlin-scope-functions.jpg" width="100%">

For instance, `apply` provides the context object via `this` and evaluates to the context object.
This means that the following expression's evaluation
```
someObject.apply {
  someMethod()
}
```
- Calls `someMethod` on `someObject` (`this` is used implicitly).
- Evaluates to `someObject`.

The table above can be used to select the most appropriate scope function for a given use case.
Just answer these two questions and use them to select the table's column and row, respectively:

- To what should the overall expression evaluate (i.e. is the action result needed or not)?
- How should the context object be made available inside the block? Typically, when calling methods on the context object the most ergonomic way is via `this`. 

Finally, in addition to the previous five scope functions, there is also a `run` overload that doesn't receive any object and essentially allows a block to be used as an expression.
