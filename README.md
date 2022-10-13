# Atomic Kotlin

## Introduction
---------------

### Compilers and Interpreters

- Compilers: A compiler is a special program that translates a programming language's source code into machine code, bytecode or another programming language. The source code is typically written in a high-level, human-readable language such as Java or C++.

- Interpreters: In computer science, an interpreter is a computer program that directly executes instructions written in a programming or scripting language, without requiring them previously to have been compiled into a machine language program.

- Kotlin is compiled rather than interpreted.

- Source Code ---------------> (Compilation) Machine Instructions or Bytecode -----------> (Run) Result.

- Languages such as C, C++, Go and Rust compile into machine code that
runs directly on the underlying hardware central processing unit (CPU).

- Languages like Java and Kotlin compile into bytecode which is an
intermediate-level format that doesn’t run directly on the hardware CPU,
but instead on a virtual machine, which is a program that executes bytecode
instructions. The JVM version of Kotlin runs on the Java Virtual Machine
(JVM).

- Garbage collection (GC) is a memory recovery feature built into programming languages such as C# and Java. A GC-enabled programming language includes one or more garbage collectors (GC engines) that automatically free up memory space that has been allocated to objects no longer needed by the program.

- Just as C++ was initially intended to be “a better C,” Kotlin was initially
oriented towards being “a better Java.” It has since evolved significantly
beyond that goal.

### Hello, World!

```
fun main() {
    println("Hello, World!")
}
```

### var, val

- var, short for variable, which means you can reassign its contents. var is mutable.

- val, short for value, which means you can only initialize it; you cannot
reassign it. val is immutable.

### Data Types

- Int, Double, String, Boolean, Char

### Functions

```
fun functionName(p1: Type1, p2: Type2, ...): ReturnType {
 lines of code
 return result
}
```

- If the function doesn’t provide a meaningful result, its return type is Unit.
You can specify Unit explicitly if you want, but Kotlin lets you omit it:

```
fun sayHello() {
 println("Return nothing!!")
}

fun sayGoodbye(): Unit {
 println("Return nothing!!")
}
```

- The main() function also returns Unit

- If a function is only a single expression, you can use the abbreviated syntax
of an equals sign followed by the expression:

```
fun multiplyByThree(x: Int): Int = x * 3
```

- A function body surrounded by curly braces is called a block body. A
function body using the equals syntax is called an expression body.

### if Expressions

```
fun main() {
 if (1 > 0)
 println("It's true!")
 if (10 < 11) {
 println("10 < 11")
 println("ten is less than eleven")
 }
}
```

- We use == to check two numbers for equality. != tests for inequality.

```
fun main() {
 val num = 10
 val result = if (num > 100) 4 else 42
 println(result)
}
```

### String Templates

- A String template is a programmatic way to generate a String.

- If you put a $ before an identifier name, the String template will insert that
identifier’s contents into the String:

```
fun main() {
 val answer = 42
 println("Found $answer!") // [1]
 println("printing a $1") // [2]
}
```

- You can also insert values into a String using concatenation (+):

```
// StringTemplates/StringConcatenation.kt
fun main() {
 val s = "hi\n" // \n is a newline character
 val n = 11
 val d = 3.14
 println("first: " + s + "second: " +
 n + ", third: " + d)
}
/* Output:
first: hi
second: 11, third: 3.14
*/
```

- Placing an expression inside ${} evaluates it. The return value is converted
to a String and inserted into the resulting String:

```
fun main() {
 val condition = true
 println(
 "${if (condition) 'a' else 'b'}") // [1]
 val x = 11
 println("$x + 4 = ${x + 4}")
}
/* Output:
a
11 + 4 = 15
*/
```

### Number Types

- Different types of numbers are stored in different ways.

### Booleans

- Boolean is a true or false values. 

### Repetition with while

- Computers are ideal for repetitive tasks.

### Looping & Ranges

- The for keyword executes a block of code for each value in a
sequence.

```
for (v in values) {
 // Do something with v
}
```

- Define range:

```
for (i in 1..3) {
 println("Hey $i!")
 }
```

- You can also produce a range of characters. This for iterates from a to z:

```
fun main() {
 for (c in 'a'..'z') {
 print(c)
 }
}
/* Output:
abcdefghijklmnopqrstuvwxyz
*/
```

- A range is an interval of values defined by a pair of endpoints. There are
two basic ways to define ranges:

```
fun main() {
 val range1 = 1..10 // [1]
 val range2 = 0 until 10 // [2]
 println(range1)
 println(range2)
}
```

- You can iterate over a range in reverse order. You can also use a step value
to change the interval from the default of 1:

```
fun showRange(r: IntProgression) {
 for (i in r) {
 print("$i ")
 }
 print(" // $r")
 println()
}
fun main() {
 showRange(1..5)
 showRange(0 until 5)
 showRange(5 downTo 1) // [1] downTo produces a decreasing range.
 showRange(0..9 step 2) // [2]
 showRange(0 until 10 step 3) // [3]
 showRange(9 downTo 2 step 3)
}
```

- Characters are stored as numbers corresponding to their ASCII codes, so
adding an integer to a character produces a new character corresponding to
the new code value:

```
fun main() {
 val ch: Char = 'a'
 println(ch + 25)
 println(ch < 'z')
}
/* Output:
z
true
*/
```

- A for loop can iterate over Strings directly:

```
fun main() {
 for (ch in "Jnskhm ") {
 print(ch + 1)
 }
}
/* Output:
Kotlin!
*/
```

- If you simply want to repeat an action a fixed number of times, you may
use repeat() instead of a for loop:

```
fun main() {
 repeat(2) {
 println("hi!")
 }
}
/* Output:
hi!
hi!
```

- repeat() is a standard library function, not a keyword.

### The in Keyword

- The in keyword tests whether a value is within a range.

- !in checks that a value doesn’t belong to a range.

```
fun notDigit(ch: Char) =
 ch !in '0'..'9'
```

### Expressions & Statements

- Statements and expressions are the smallest useful fragments of code
in most programming languages.

- There’s a basic difference: a statement has an effect, but produces no result.
An expression always produces a result.

- A statement changes state.

- An expression expresses.

## SECTION II: INTRODUCTION TO OBJECTS

- Objects are the foundation for numerous modern languages, including
Kotlin.

### Constructors

- You initialize a new object by passing information to a constructor.

- Name not accessible outside of class.

```
class Alien(name: String) {
 val greeting = "Poor $name!"
}
```

- Name accessible outside of class.

- When name is defined as a var or val, it becomes a property and is thus
accessible outside the constructor. val constructor parameters cannot be
changed, while var constructor parameters are mutable.

### Packages

- You can name the source-code file anything you like, unlike Java which
requires the file name to be the same as the class name.

```
class MutableNameAlien(var name: String)
class FixedNameAlien(val name: String)
```

### Lists

- A List is a container, which is an object that holds other objects.

### Variable Argument Lists

- The vararg keyword produces a flexibly-sized argument list.

## SECTION III: USABILITY

- Computer languages differ not so much in what they make possible,
but in what they make easy—Larry Wall, inventor of the Perl
language

### Extension Functions

- Suppose you discover a library that does everything you need …
almost. If it only had one or two additional member functions, it would
solve your problem perfectly.

### Named & Default Arguments

- You can provide argument names during a function call.

### Overloading

- Languages without support for default arguments often use
overloading to imitate that feature.

### when Expressions

- A large part of computer programming is performing an action when a
pattern matches.

```
when (i) { // [1]
 1 -> "erste" // [2]
 3 -> "dritte"
 7 -> "siebte"
 8 -> "achte"
 20 -> "zwanzigste"
 else -> numbers.getValue(i) + "te" // [3]
 }
```

```
when (choice) {
 yes -> trace("Hooray!")
 no -> trace("Too bad!")
 }
```

```
when (input) { // [1]
 "up", "u" -> coordinates.y-- // [2]
 "down", "d" -> coordinates.y++
 "left", "l" -> coordinates.x--
 "right", "r" -> { // [3]
 trace("Moving right")
 coordinates.x++
 }
 "nowhere" -> {} // [4]
 "exit" -> return // [5]
 else -> trace("bad input: $input")
 }
```

```
when (setOf(first, second)) {
 setOf("red", "blue") -> "purple"
 setOf("red", "yellow") -> "orange"
 setOf("blue", "yellow") -> "green"
 else -> "unknown"
 }
```

- The solution using when is a more elegant way to choose between several
options.

### Enumerations

- An enumeration is a collection of names.

```
enum class Level {
 Overflow, High, Medium, Low, Empty
}

fun main() {
 Level.Medium eq "Medium"
}

```

```
enum class Direction(val notation: String) {
    North("N"),
    South("S"),
    East("E"),
    West("W");

    val opposite: Direction get() =
        when(this) {
            North -> South
            South -> North
            East -> West
            West -> East
        }
}

fun main() {
    val direction = North.opposite
    println(direction)
}
```

### Data Classes

- Kotlin reduces repetitive coding.

```
data class Simple(
 val arg1: String,
 var arg2: Int
)
fun main() {
 val s1 = Simple("Hi", 29)
 val s2 = Simple("Hi", 29)
 s1 eq "Simple(arg1=Hi, arg2=29)"
 s1 eq s2
}

```

- The diffrance between class object and data class object in equality, If you define the same instance of class objects it should have diffrent address in memory, but data class have the same istance and same equality.

### Destructuring Declarations

- Suppose you want to return more than one item from a function, such
as a result along with some information about that result.

```

fun compute(input: Int): Pair<Int, String> =
    if(input > 5) {
        Pair(5, "Low")
    } else {
        Pair(10, "High")
    }


fun main() {
    val result = compute(5)

    println("First Value: ${result.first}")
    println("Second Value: ${result.second}")

}

```

```

fun main() {
    val (f, s) = compute(5)

    println("First Value: $f")
    println("Second Value: $s")

}

```

- data Classes automatically allow destructuring declarations:

```

data class Computation(
 val data: Int,
 val info: String
)
fun evaluate(input: Int) =
 if (input > 5)
 Computation(input * 2, "High")
 else
 Computation(input * 2, "Low")
fun main() {
 val (value, description) = evaluate(7)
 value eq 14
 description eq "High"
}

```

- Tuples:

```

data class Tuple(
 val i: Int,
 val d: Double,
 val s: String,
 val b: Boolean,
 val l: List<Int>
)
fun main() {
 val tuple = Tuple(
 1, 3.14, "Mouse", false, listOf())
 val (i, d, s, b, l) = tuple
 i eq 1
 d eq 3.14
 s eq "Mouse"
 b eq false
 l eq listOf()
 val (_, _, animal) = tuple // [1]
 animal eq "Mouse"
}

```

### Nullable Types

- Consider a function that sometimes produces “no result.” When this
happens, the function doesn’t produce an error per se. Nothing went
wrong, there’s just “no answer.”

### Safe Calls & the Elvis Operator

- Kotlin provides convenient operations for handling nullability.

- The Elvis operator: `?:`.

### Non-Null Assertions

- A second approach to the problem of nullable types is to have special
knowledge that the reference in question isn’t null.

- Non null assertion: `!!`.

### Extensions for Nullable Types

- Sometimes it’s not what it looks like.

### Introduction to Generics

- Generics create parameterized types: components that work across
multiple types.

### Generic Functions

- To define a generic function, specify a generic type parameter in angle
brackets before the function name:

```

fun <T> identity(arg: T): T = arg

fun main() {
 identity("Yellow") eq "Yellow"
 identity(1) eq 1
 val d: Dog = identity(Dog())
 d.bark() eq "Ruff!"
}

```

### Extension Properties

- Just as functions can be extension functions, properties can be
extension properties.

### break & continue

- break and continue allow you to “jump” within a loop.

## SECTION IV: FUNCTIONAL PROGRAMMING

- The unavoidable price of reliability is simplicity.

### Lambdas

- Lambdas produce compact code that’s easier to understand.

### The Importance of Lambdas

- Lambdas may seem like syntax sugar, but they provide important
power to your programming.

### Operations on Collections

- An essential aspect of functional languages is the ability to easily
perform batch operations on collections of objects.

### Member References

- You can pass a member reference as a function argument.

### Higher-Order Functions

- A language supports higher-order functions if its functions can accept
other functions as arguments and produce functions as return values.

### Manipulating Lists

- Zipping and flattening are two common operations that manipulate
Lists.

#### Zipping

- zip() combines two Lists by mimicking the behavior of the zipper on your
jacket, pairing adjacent List elements:

```
fun main() {
 val left = listOf("a", "b", "c", "d")
 val right = listOf("q", "r", "s", "t")
 left.zip(right) eq // [1]
 "[(a, q), (b, r), (c, s), (d, t)]"
 left.zip(0..4) eq // [2]
 "[(a, 0), (b, 1), (c, 2), (d, 3)]"
 (10..100).zip(right) eq // [3]
 "[(10, q), (11, r), (12, s), (13, t)]"
}

```

```

data class Person(
 val name: String,
 val id: Int
)
fun main() {
 val names = listOf("Bob", "Jill", "Jim")
 val ids = listOf(1731, 9274, 8378)
 names.zip(ids) { name, id ->
 Person(name, id)
 } eq "[Person(name=Bob, id=1731), " +
 "Person(name=Jill, id=9274), " +
 "Person(name=Jim, id=8378)]"
}

```

- To zip two adjacent elements from a single List, use zipWithNext():

```

import atomictest.eq
fun main() {
 val list = listOf('a', 'b', 'c', 'd')
 list.zipWithNext() eq listOf(
 Pair('a', 'b'),
 Pair('b', 'c'),
 Pair('c', 'd'))
 list.zipWithNext { a, b -> "$a$b" } eq
 "[ab, bc, cd]"
}

```

#### Flattening

- flatten() takes a List containing elements that are themselves Lists—a
List of Lists—and flattens it into a List of single elements:

```

// ManipulatingLists/Flatten.kt
import atomictest.eq
fun main() {
 val list = listOf(
 listOf(1, 2),
 listOf(4, 5),
 listOf(7, 8),
 )
 list.flatten() eq "[1, 2, 4, 5, 7, 8]"
}

```

### Building Maps

- Maps are extremely useful programming tools, and there are numerous
ways to construct them.

```

data class Person(
 val name: String,
 val age: Int
)
val names = listOf("Alice", "Arthricia",
 "Bob", "Bill", "Birdperson", "Charlie",
 "Crocubot", "Franz", "Revolio")
val ages = listOf(21, 15, 25, 25, 42, 21,
 42, 21, 33)
fun people(): List<Person> =
 names.zip(ages) { name, age ->
 Person(name, age)
 }

```

### Sequences

- A Kotlin Sequence is like a List, but you can only iterate through a
Sequence—you cannot index into a Sequence. This restriction
produces very efficient chained operations.

### Local Functions

- You can define functions anywhere—even inside other functions.

### Folding Lists

- fold() combines all elements of a list, in order, to generate a single
result.

```

fun main() {
 val list = listOf(1, 10, 100, 1000)
 list.fold(0) { sum, n ->
 sum + n
 } eq 1111
}

```

## SECTION V: OBJECT-ORIENTED PROGRAMMING

- … inheritance is a very flexible mechanism. It’s possible and in fact
fairly common to misuse it, but that’s not a reason to distrust it
systematically as seems to have become the fashion.—Bertrand
Meyer

### Interfaces

- An interface describes the concept of a type. It is a prototype for all
classes that implement the interface.