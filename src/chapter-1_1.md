# Javascript Game Programming for Beginners
(c) 2016 Eric Balingit  

<br>
<br>
### Chapter 1 Section 1 - Varibles, Arrays, Loops and Logic

<br>
#### Variables in Javascript

The first thing you need to know about Javascript, or any language, is how to
create and define _**variables**_.  A variable in Javascript is basically a
name that refers to some value.  That value may be a **primitive value**, such
as a _number_ or a _string_, or an _object_ - a grouping of one or more kinds
of data such as numbers, text characters as in a _string_, program code, or even
other objects.  The reason we use variables is because we need to do
computations with things, and to do that we need to be able to refer to the
_values_ associated with those things that we wish to perform computations on.
 This is much easier to do if we can refer to those things by their _variable
name_.  Variable names, like many other concepts we will encounter in
programming, exist for the purpose of providing flexibility and making our job,
as programmers, easier.  Below is a table for the kinds of variables, also known
as _**variable types**_ that we have to work with in Javascript.

<h5 id="table-1_1">Table 1.1</h5>
|type      |example   |
|:---------|:---------|
|_number_  |`0, 1, 2, 1.38e37, -3, -2.15e-12`|
|_string_  |`"Javascript", "word", "thing"`|
|_object_  |`{}, []`|
|_function_|`var aPlusB = function ( a, b ) { return a + b; }`|
###### _Javascript variable types_

The last type, _function_, is a bit more complicated.  We will talk about that
one in section 1.2.  For now let us focus on the simpler kinds of variables,
_number_, _string_, and _object_.

The first and fundamentally most important type of variable is a _number_.  It
may be hard to see at first, but everything imaginable in the world of
programming is built on numbers, even the mysterious and complicated inner
workings of the function in the table above, not the adding that it does, but
the function itself, deep down inside the computer.  This is because numbers are
the only thing that computers know how to do computations with.  In order to get
started working with some numeric variables, let us see how a variable can be
defined and given a value in Javascript.

```
var x = 5;
var name = "Robert";
var timesInSeconds = [ 9.81, 9.84, 9.92, 10.0, 10.32 ];
```

The use of the name, _x_, is simply conventional to use in examples.  It is the
first variable that we learn how to work with in pre-algebra, but the name of
the variable could be any valid _identifier_.  In Javascript, variable names,
or _identifiers_ may contain one or more alpha-numeric characters (a-z, A-Z,
0-9) and/or the characters *`_`* and *`$`* as long as the first character of the
identifier does not start with a numeric character *`0-9`*.  The first word of
the above line of code, in programming one or more lines of code which perform a
task is called a _statement_, is referred to as a _key word_.  A _key word_ in
any programming language is a reserved word that can only be used by the program
if it is used with correct grammar, or _syntax_, and cannot be used for anything
other than its intended purpose in that language.  For example, I could not name
a variable *`var`* because that would produce an error in my program.  So the
above statements _declare_ variables named *`x`*, *`name`* and *`timeInSeconds`*
and gives each a value, *`5`*, *`"Robert"`* and the array *`[ 9.81, 9.84, 9.92,
10.0, 10.32 ]`* respectively.  These kinds of statements can be referred to in
several ways, as a _declarations_, _variable declarations_, or _declaration and
assignment statements_ because the values are _assigned_ to the variable names
when they are _declared_.

You may wonder about the last identifier in the above code snippet.  Some of the
letters are upper case and some are lower case.  This is another convention
called _Camel Case_.  It is not a requirement, but merely a preference.  Some
programmers like to use underscore instead like *`time_in_seconds`*.  I tend to
switch back and forth depending on the circumstances, preferring the underscore,
*`_`*, to separate words or abbreviations in an indentifying phrase.  The point
to take away here is that variable names should be descriptive so that you, the
programmer, and anyone else, other programmers, can read and understand what the
code is about.  Good variable names help, which depending on the circumstances
*`x`* may or may not be a good choice, to clarify the intent of the code for
anyone who looks at it, most importantly for you several days, weeks or months
after it was written.

<br>
#### Arrays Can Hold Lots of Things

The array we looked at previously held several numeric values, but in principle,
arrays in Javascript can hold any kind of value, as in any variable _type_ found
in <a class="local" href="#table-1_1">Table 1.1</a>.  Before we go on to examine
much more about arrays, lets take a step forward just to visit an idea related
to _objects_ and that is called *_properties_*.  Properties are things that are
associated with objects in a programming language.  We will go into more detail
about that later, but for dealing with arrays, it helps to have a heads up on
this idea.  The way that we access properties of objects in Javascript, and in
most programming languages, is by using the *_dot operator_*.  Operators are
basic symbols in a programming language, like symbols in math - typically single
characters that perform a function.  We've seen at least one operator already
and that is the _assignment_ operator, or `=`.  The dot operator is a dot, very
much like the period at the end of this sentence.  And like the period at the
end of a sentence, the dot operator comes after the identifier for an object.
 What we are interested in for now is the `length` property of the array.  Below
is an example, which I will describe in detail, which demonstrates how arrays
can be useful.

```
// all recorded times
var timesInSeconds = [ 9.81, 9.84, 9.92, 10.0, 10.32 ];

// a variable to compute the average time
var averageTime = 0;

// sum all of the recorded times
for ( var i = 0; i < timeInSeconds.length; i++ ) {
    averageTime = averageTime + timeInSeconds [ i ];
}

// compute the average
averageTime = averageTime / timeInSeconds.length;
```

<br>
<br>
|Back      |Forward   |
|:---------|---------:|
|[Back to Chapter 1](#chapter-1)|[On to Section 1.2](#chapter-1_2)|

|          |
|:--------:|
|[Table of Contents](#TOC)