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



















