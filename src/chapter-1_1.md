# Javascript Game Programming for Beginners
(c) 2016 Eric Balingit  

<br>
<br>
### Chapter 1 Section 1 - Varibles, Arrays, Loops and Logic

<br>
#### Variables in Javascript

The first thing you need to know about Javascript, or any language, is how to
create and define _*variables*_.  A variable in Javascript is basically a
name that refers to some value.  That value may be a **primitive value**, such
as a _number_, a _string_ or a _boolean_, or an _object_.  Objects are
"groupings" of one or more kinds of data such as numbers in an array, text
characters as in a _string_[^1], program code in the form of _functions_, or
even other objects.  The reason we use variables is because we need to
do computations with things, and to do that we need to be able to refer to the
_values_ associated with those things that we wish to perform computations on.
 This is much easier to do if we can refer to those things by their _variable
name_.  Variable names, like many other concepts we will encounter in
programming, exist for the purpose of providing flexibility and making our job,
as programmers, easier.  Below is a table for the kinds of variables, also known
as _*data types*_, that we have to work with in Javascript.

[^1]: Strings in Javascript are considered primitive data types due to their
immutability under the hood.  Being _immutable_ means that once a string is
declared and given a value, the underlying value never changes, even though
strings may be put together, end-to-end, by _concatenation_.  When that happens
the new string is not the same thing as the previous strings according to how
Javascript works internally.  It is also worth noting that all primitive types
in Javascript have an equivalent Object type that can be used to contain and
operate on the primitive value.  Those Object types are built from the native
classes Number, Boolean, and String.  More information about types will be
provided in [Chapter 2.4](#chapter-2_4).

<h5 id="table-1_1">Table 1.1</h5>
|type      |example   |
|:---------|:---------|
|_number_  |`0, 1, 2, 1.38e37, -3, -2.15e-12`|
|_boolean_ |`true, false`|
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

<h5 id="example-1_1">Example 1.1</h5>
``` js
var x = 5;
var name = "Robert";
var timesInSeconds = [ 9.81, 9.84, 9.92, 10.0, 10.32 ];
```
###### _Declaring and Assigning Variables_

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
#### Arrays Can Hold Lots of Things, Loops Help with Heavy Lifting

The array we looked at previously held several numeric values, but in principle,
arrays in Javascript can hold any kind of value, as in any variable _type_ found
in <a class="local" href="#table-1_1">Table 1.1</a>.  Before we go on to examine
much more about arrays, lets take a step forward just to visit an idea related
to _objects_ and that is called _*properties*_.  Properties are things that are
associated with objects in a programming language.  We will go into more detail
about that later, but for dealing with arrays, it helps to have a heads up on
this idea.  The way that we access properties of objects in Javascript, and in
most programming languages, is by using the _*dot operator*_.  Operators are
basic symbols in a programming language, like symbols in math - typically single
characters that perform a function.  We've seen at least one operator already
and that is the _assignment_ operator, or `=`.  The dot operator is a dot, very
much like the period at the end of this sentence.  And like the period at the
end of a sentence, the dot operator comes after the identifier for an object.
 What we are interested in for now is the `length` property of the array.  Below
is an example, which I will describe in detail, which demonstrates how arrays
can be useful.

<h5 id="example-1_2">Example 1.2</h5>
``` js
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

// display the result
println ( "The average time is " + averageTime );
```
###### _Using Arrays to Process Data_

<br>
Without using an array we could have written the following:

<h5 id="example-1_3">Example 1.3</h5>
``` js
// compute the average time
var averageTime = ( 9.81 + 9.84 + 9.92 + 10.0 + 10.32 ) / 5;
```
###### _Computing with Literal Values_

This may look more concise, indeed it is only a single line of code as compared
to the six lines above ( not including comments ), however, imagine that we
have a **lot** of numbers, more than a hundered, or even more than a thousand.
 It is not unreasonable to deal with that much data, even in a small program or
game, and it is even nicer if your program can generate such data for you
without you having to type any of it out.  We will discuss more ways of handling
large amounts of data as we move through this book.  For now, let us have
another look at that odd looking `for ( blah; blah; blah )` thing and see what
it all means.

The complete structure in <a class="local" href="#example-1_2">example 1.2</a>
that begins with `for`, performs a bit of logic inside the parethesis, between
`(` and `)`, and houses some code in curly brackets, between `{`, and `}`, is
called a _*for loop*_.  Notice that it is **not** terminated with a semi-colon
after the last `}`, which means that it is technically a _structure_ rather than
a _statement_.  Statements do end with `;`.  The opening and closing curly
braces are the beginning and end of the contained _code block_ of the loop.  The
code block is run as many times as the logic evaluates to `true` inside the
parenthesis.  The code that gets run `averageTime = averageTime + timeInSeconds
[ i ];` is simple enough.  What it says is:

> "Assign the value of the sum, `averageTime` plus the value at the index, `i`,
in the array `timeInSeconds`, to the variable named `averageTime`."

<p class="no-indent">To put it another way, you could say:</p>

> "Retrieve the value in the variable named `averageTime` and hold onto it, now
retrieve the value at the index of `i` in the varaible named `timeInSeconds`,
now add that value to the other value you are holding and give the result back
to the variable named `averageTime`."

The second is closer to how the computer would actually interpret such code.
Can you see how the description gets longer and more detailed the further away
we get from the code that we have typed, and closer to how the computer actually
sees what we have written?  This is important to consider when writing programs.
Even at this very early stage of your education in programming, you should
always try to keep in the back of your mind some notion of what the computer is
actually trying to do with the code that you give to it.  Everyone who programs,
at some point, uses someone else's example and works with objects or structures
that are unfamiliar.  If you are confused about what a piece of code is doing,
ask!  <a class="external" href="http://stackoverflow.com/">Stack Overflow</a>
is a great place to find answers to questions you may have or to post questions
where the already provided answers do not exactly help with your specific
question.

#### The Logic of Loops

There are a few different kinds of loops in Javascript: `for(){}` loops ( called
a "for loop", `while(){}` loops ( called a "while loop" ) and `do{}while()`
loops ( called a "do loop" or a "do while loop".  Each type has a structure that
contains both a set of parenthesis `()` and a set of curly braces `{}`.  The
parenthesis contains the logic which determines _whether_ or _how many times_
the loop should execute.  The curly braces contains the code that will be
executed.  Whether or how many times the code is executed depends on the kind of
loop as well as the logic inside the parenthesis.  There are only two things to
remember to determine *whether* the code inside the loop will be executed.

 - *`for`* loops and *`while`* loops execute _zero or more times depending on
the logic inside the parenthesis_
 - *`do while`* loops execute _one or more times depending on the logic inside
the parenthesis_

Did you catch the difference?  A `do while` loop always executes at least once,
then may execute subsequently depending on the logic provided to it.  Both `for`
and `while` loops may execute, or not depending on the logic provided to them.
It seems like a subtle difference, but it is an important difference.  The most
common type of loop that programmers use is the `for` loop _because it can
capture the behavior of both of the other kinds of loops_.  However, in certain
circumstances, the necessary logic may be simpler when using a `while` loop or
a `do while` loop.  Here is the logic that controls the `for` loop in
<a class="local" href="#example-1_2">Example 1.2</a> step by step:

<h5 id="example-1_4">Example 1.4</h5>
``` js
for ( var i = 0; i < timeInSeconds.length; i++ ) {
    averageTime = averageTime + timeInSeconds [ i ];
}
```
<p class="no-indent">And we will focus on this:</p>
``` js
var i = 0; i < timeInSeconds.length; i++
```
###### _The logic of the `for` loop in Example 1.2_

 1. The first part, `var i=0;` is called the _*initialization statement*_.  It
declares a variable `i` and gives it the value `0`.
 2. The second part, `i < timeInSeconds.length;` is called the _*conditional statement*_,
this is what determines how many times the loop will execute, if at all.
 3. The third part, `i++` is the odd one.  As of this writing [wikipedia](https://en.wikipedia.org/wiki/For_loop#Traditional_for-loops)
refers to this statement as the _[afterthought](https://en.wikipedia.org/wiki/Code_cleanup)_
which links to something completely unrelated, until you get to the very bottom
of the article and find [loop cleanup](https://en.wikipedia.org/wiki/Code_cleanup#Loop_Cleanup)
which itself seems a dubious term.  Given that the first two parts in this 
are less hazardous in appearance ( though every bit as important as the _*loop
cleanup statement*_ ), we will handle the cleanup statement first.

Note that the loop cleanup statement does not have a _terminating symbol_, `;`,
like the others do.  The two plus signs, `++`, are called an _increment
operator_.  What they do is _increment_ or simply add one to the value of the
variable that they operate on, in this case `i`.  There are two kinds of
increment operators, _*post increment*_ and _*pre increment*_.  This kind, `i++`
is a _post increment operator_ and it is easy to remember because it appears
after the variable ( post ), whereas the other kind would place the plus signs
before the variable ( pre ).  For now, as far as this loop is concerned, we will
simply consider that the effect that is happening to the variable `i` is
equivalent to the statement `i = i + 1`, similar to the code that the for loop
executes which we discussed in the previous section.  I will give more details
on increment and decrement, `--`, operators in the section in this chapter on
Operators.



#### Say Hello to George Boole

The data type _boolean_ in <a class="local" href="#table-1_1">Table 1.1</a> is
named after the founder of the system of mathematics that underlies all modern
information technology, <a class="external" href="https://en.wikipedia.org/wiki/George_Boole">George Boole</a>.
 The system of mathematics that underlies information technology is called
<a class="external" href="https://en.wikipedia.org/wiki/Boolean_algebra">Boolean Algebra</a>[^2].

[^2]: Unfortunately Khan Academy does not have any videos or material
specifically on Boolean Algebra.  I think it is important.  If you want to
request this topic, vote and comment on this topic on
[Khan Academy Zendesk #201470924-Discrete-Mathematics](https://khanacademy.zendesk.com/hc/en-us/community/posts/201470924-Discrete-Mathematics).
Note that Discrete Mathematics is a subject which covers Boolean Algebra as well
as other areas of math which are more advanced, college-level mathematics
subjects.  Boolean Algebra is perfectly accessible to beginning programmers or
anyone with a pre-algebra level mathathematics background.

<br>
<br>
|Back      |Forward   |
|:---------|---------:|
|[Back to Chapter 1](#chapter-1)|[On to Section 1.2](#chapter-1_2)|

|          |
|:--------:|
|[Table of Contents](#TOC)