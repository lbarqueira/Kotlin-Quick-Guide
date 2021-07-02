Kotlin Quick Guide for Android Basics in Kotlin
===============================================

This Kotlin Quick Guide summarizes the topics covered in the [Android Basics in Kotlin course](https://developer.android.com/courses/android-basics-kotlin/course) in the form of code snippets.

Learn more
----------

-   See the [Kotlin Language Documentation](https://kotlinlang.org/docs/reference/) for full reference.
-   See the [Kotlin Koans](https://play.kotlinlang.org/koans/overview) for more snippets to practice with. **Note**: This brings you to an external kotlinlang.org site that is developed by JetBrains.


[Unit 1](https://developer.android.com/courses/android-basics-kotlin/unit-1)
----------------------------------------------------------------------------

### Kotlin programs

**The smallest `main()` program for printing text**

```kotlin
fun main() {
    println("Hello, world!")
}
```

**Printing a line of text**

```kotlin
println("This is the text to print!")
```

**Inline comments**

```kotlin
// This is a comment line.
// This is another comment.
```

**Variables**

```kotlin
// Assign once, cannot change.
val age = "5"
val name = "Rover"

// Assign and change as needed.
var roll = 6
var rolledValue: Int = 4
```

**Printing variables with string templates**

```kotlin
println("You are already ${age}!")
println("You are already ${age} days old, ${name}!")
```

**Data types**

```kotlin
Int       // Whole positive and negative numbers and zero
String    // Piece of text between quotes
IntRange  // Setting a range such as 1..6
Boolean   // Can only be true or false
```

**Function without arguments**

```kotlin
// Define the function.
fun printHello () {
    println ("Hello Kotlin")
}

// Call the function.
printHello()
```

**Function with arguments**

```kotlin
fun printBorder(border: String, timesToRepeat: Int) {
    repeat(timesToRepeat) {
        print(border)
    }
    println()
}
```

**Function that returns a value**

```kotlin
fun roll(): Int {
     val randomNumber = (1..6).random()
     return randomNumber
}
```

**Basic operators**

```kotlin
*     // multiplication
/     // division
+     // addition
-     // subtraction
=     // assignment
```

**Logic operators**

```kotlin
>    // greater than
<    // less than
==   // equal
>=   // greater or equal
<=   // less or equal
!=   // not equal
```

**Creating random numbers**

```kotlin
val randomNumber = diceRange.random()

fun roll() {
     val anotherRandomNumber = (1..6).random()
     println(randomNumber)
}
```

### Controlling program flow

**Repeating an action with `repeat()`**

```kotlin
fun printBorder() {
    repeat(23) {
        print("=")
    }
}
```

**Nesting `repeat()` loops**

```kotlin
fun printCakeBottom(age: Int, layers: Int) {
    repeat(layers) {
        repeat(age + 2) {
            print("@")
        }
        println()
    }
}
```

**Conditional statements with `if`/`else`**

```kotlin
fun main() {
   val num = 4
   if (num > 4) {
       println("The variable is greater than 4")
   } else if (num == 4) {
       println("The variable is equal to 4")
   } else {
       println("The variable is less than 4")
   }
}
```

**Conditional statements with `when`**

```kotlin
when (rollResult) {
    luckyNumber -> println("You won!")
    1 -> println("So sorry! You rolled a 1. Try again!")
    2 -> println("Sadly, you rolled a 2. Try again!")
    3 -> println("Unfortunately, you rolled a 3. Try again!")
    4 -> println("No luck! You rolled a 4. Try again!")
    5 -> println("Don't cry! You rolled a 5. Try again!")
    6 -> println("Apologies! you rolled a 6. Try again!")
}
```

**Assigning the result of a `when` statement to a variable**

```kotlin
// Determine which drawable resource ID to use based on the dice roll.
val drawableResource = when (diceRoll) {
    1 -> R.drawable.dice_1
    2 -> R.drawable.dice_2
    3 -> R.drawable.dice_3
    4 -> R.drawable.dice_4
    5 -> R.drawable.dice_5
    else -> R.drawable.dice_6
}
```

### Classes

**Simple class with property and method**

```kotlin
class Dice {
    var sides = 6

    fun roll() {
        val randomNumber = (1..6).random()
        println(randomNumber)
    }
}
```

**Class with parameter**

```kotlin
class Dice (val numSides: Int) {

    fun roll(): Int {
        val randomNumber = (1..numSides).random()
        return randomNumber
    }
}
```

**Creating instances**

```kotlin
val myFirstDice = Dice(6)
```

[Unit 2](https://developer.android.com/courses/android-basics-kotlin/unit-2)
----------------------------------------------------------------------------

### Classes

**Abstract class**

```kotlin
abstract class Dwelling() {
}
```

**Abstract class with an abstract property**

```kotlin
abstract class Dwelling() {
    abstract val buildingMaterial: String
}
```

**Abstract class with an abstract method**

```kotlin
abstract class Dwelling() {
    abstract fun floorArea(): Double
}
```

**Mark a class `open` so it can be subclassed**

```kotlin
open class RoundHut(residents: Int) {
}
```

**Create a subclass by extending a parent class**

```kotlin
class SquareCabin : Dwelling()
```

**Override a function from a superclass**

```kotlin
override fun floorArea(): Double {
}
```

**Call the superclass implementation of a function**

```kotlin
override fun floorArea(): Double {
    return super.floorArea() * floors
}
```

### Lists

**Define a read-only list**

```kotlin
val numbers = listOf(1, 2, 3, 4, 5, 6)
```

**Get the size of the list**

```kotlin
numbers.size
```

**Get the first item of a list**

```kotlin
numbers[0]
```

**Get a copy of a list in reverse order**

```kotlin
listOf("red", "blue", "green").reversed()
```

**Define a mutable list of strings**

```kotlin
val entrees = mutableListOf<String>()
```

**Add an item to a mutable list**

```kotlin
entrees.add("spaghetti")
```

**Modify an item in a mutable list**

```kotlin
entrees[0] = "lasagna"
```

**Remove an item from a mutable list**

```kotlin
entrees.remove("lasagna")
```

### Loops

**Use `for` loop to iterate over items in a list**

```kotlin
for (element in myList) {
    // Perform an operation with each item
    println(element)
}
```

**Use `while` loop to iterate over items in a list**

```kotlin
var index = 0
while (index < myList.size) {
    println(myList[index])
    index++
}
```

### Strings

**Number of characters in a String**

```kotlin
val name = "Android"
println(name.length)
```

**Use a variable in a String template**

```kotlin
val number = 10
println("$number people")
```

**Use an expression in a String template**

```kotlin
val number = 10
val groups = 5
println("${number * groups} people")
```

### Miscellaneous

**Augmented assignments**

```kotlin
a += b   // a = a + b
a -= b   // a = a - b
a *= b   // a = a * b
a /= b   // a = a / b
```

**Use `with` to simplify access to an object**

```kotlin
with(squareCabin) {
    println("Capacity: ${capacity}")
    println("Material: ${buildingMaterial}")
    println("Has room? ${hasRoom()}")
}
```

**Import from the Kotlin math library**

```kotlin
import kotlin.math.PI
```

**Use fully qualified name for a constant in the Kotlin math library (no import statement needed)**

```kotlin
kotlin.math.PI * radius * radius
```

**Chain calls together (for accessing properties and calling methods)**

```kotlin
val stringInTextField = binding.costOfService.text.toString()
```

**Variable number of function arguments**

```kotlin
fun addToppings(vararg val toppings: String)
```

**Package declaration**

```kotlin
package com.example.affirmations.model
```

[Unit 3](https://developer.android.com/courses/android-basics-kotlin/unit-3)
----------------------------------------------------------------------------

### Sets

**Create a set from a list**

```kotlin
val numbers = listOf(0, 3, 8, 4, 0, 5, 5, 8, 9, 2)
val setOfNumbers = numbers.toSet()
```

**Define a set**

```kotlin
val set1 = setOf(1,2,3)
val set2 = mutableSetOf(3, 4, 5)
```

**Set operations**

```kotlin
set1.intersect(set2) // 3
set1.union(set2) // 1, 2, 3, 4, 5
```

### Maps

**Define a mutable map**

```kotlin
val peopleAges = mutableMapOf<String, Int>(
    "Fred" to 30,
    "Ann" to 23
)
```

**Set a value in a mutable map**

```kotlin
peopleAges.put("Barbara", 42)
peopleAges["Joe"] = 51
```

### Collection Operations

**Iterate over a collection**

```kotlin
peopleAges.forEach { print("${it.key} is ${it.value}, ") }
// Fred is 31, Ann is 23, Barbara is 42, Joe is 51,
```

**Transform each item in a collection**

```kotlin
println(peopleAges.map { "${it.key} is ${it.value}" }.joinToString(", ") )
// Fred is 31, Ann is 23, Barbara is 42, Joe is 51
```

**Filter the items in a collection**

```kotlin
val filteredNames = peopleAges.filter { it.key.length < 4 }
println(filteredNames)
// {Ann=23, Joe=51}
```

**Other collection operations**

```kotlin
val words = listOf("about", "acute", "balloon", "best", "brief", "class")
val filteredWords = words.filter { it.startsWith("b", ignoreCase = true) }
    .shuffled() // [brief, balloon, best]
    .take(2) // [brief, balloon]
    .sorted() // [balloon, brief]
```

### Scope functions

**let**

```kotlin
arguments?.let {
    letterId = it.getString(LETTER).toString()
}
```

**apply**

```kotlin
binding?.apply {
    ...
    flavorFragment = this@FlavorFragment
}
```

### Miscellaneous

**Backing property**

```kotlin
private var _currentScrambledWord = "test"
val currentScrambledWord: String
    get() = _currentScrambledWord
```

**Safe calls**

```kotlin
val letterId = intent?.extras?.getString("letter").toString()
```

**Lambda functions**

```kotlin
val triple: (Int) -> Int = { a: Int -> a * 3 }
println(triple(5))
```

**Companion objects**

```kotlin
class DetailActivity: AppCompatActivity() {

    ...

    companion object {
        const val LETTER = "letter"
    }

    ...

}

// accessible outside DetailActivity
DetailActivity.LETTER
```

**Property delegation**

```kotlin
// syntax
var <property-name> : <property-type> by <delegate-class>()
// example
private val viewModel: GameViewModel by viewModels()
```

**Late initialization**

```kotlin
private var wordsList: MutableList<String> = mutableListOf() // has a value at initialization
private lateinit var currentWord: String // needs to be assigned after initialization
```

**Elvis operator**

```kotlin
var quantity : Int? = null
quantity ?: 0 // 0
quantity = 4
quantity ?: 0 // 4
```

[Unit 4](https://developer.android.com/courses/android-basics-kotlin/unit-3)
----------------------------------------------------------------------------

### Coroutines

**Declare a suspend function**

```kotlin
suspend fun getValue(): Double {
    // long running work or calls to other suspend functions
}
```

**Run a suspend function in the GlobalScope**

```kotlin
GlobalScope.launch {
    val output = getValue()
}
```

**Call suspend function from another suspend function.**

```kotlin
suspend fun processValue() {
    val value = getValue()
    // modify the value
}
```

**Access a coroutine Job**

```kotlin
val job: Job = GlobalScope.launch {
    val output = getValue()
}
```

**Cancel a coroutine Job**

```kotlin
job.cancel()
```

**Run a suspend function and block the current thread until the function completes**

```kotlin
runBlocking {
    val output = getValue()
}
```

**Use async to make a suspend function deferable**

```kotlin
runBlocking {
    val output = await { getValue() }

    println("Output is ${output.await()}")
}
```

### Miscellaneous

**Declare an object**

```kotlin
object DataProviderManager {

}
```

**Catch an exception**

```kotlin
try {
    // code that may throw an error
} catch (exception: Exception) {
    // handle the thrown exception
}
```

**Create an enum class**

```kotlin
enum class Direction {
    NORTH, SOUTH, WEST, EAST
}
```

**Access an enum class value**

```kotlin
val direction = Direction.NORTH
```

**Check enum values**

```kotlin
when (direction) {
    Directon.NORTH -> {

    }
    Direction.SOUTH -> {

    }
    Direction.WEST -> {

    }
    Direction.EAST -> {

    }
}
```


Last updated 2021-05-06 UTC.
