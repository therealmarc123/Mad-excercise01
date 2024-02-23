# MAD - Exercise 01
## Tasks
* Watch the Kotlin Crashcourse Video in Moodle or complete the tutorials **[Introduction to programming in Kotlin](https://developer.android.com/courses/pathways/android-basics-compose-unit-1-pathway-1)** and **[Kotlin fundamentals](https://developer.android.com/courses/pathways/android-basics-compose-unit-2-pathway-1
)**.
* Answer the questions inside this Readme.md file and push it to your repository.
* Submit your coding solution of the Number Guessing Game inside the repository.
* Submit the link to your repository in Moodle.

## Questions
### Describe how Kotlin handles null safety. What are nullable types and non-null types in Kotlin? (0,5 points)

> Note: you can also use code snippets to illustrate your answer. 

<span style="color:blue"> Answer: Kotlin defines all Types as non-null by default! This implies that also by default null pointer exceptions are prevented during the complietime already rather than assertion at runtime.
So, a type of variable cannot be null, no matter the type. If this happens anyway an complie error will appear! 

```kotlin 
val a: String = "value" // non-null type
```
This obviosly works, because there is no null value is involved!

```kotlin 
val a: String = null // non-null type
```
This won't work, it will lead to an error during compilation!

If we want to counter this we need to append the operator '?' to the type as follows.

```kotlin 
val a: String? = null // null is possible
```

Now a can hold the value null

</span>


### What are lambda expressions and higher order functions in Kotlin? Why would you store a function inside a variable? (0,5 points)

<span style="color:blue">The Lambda expressions are short, anonymous functions defined with {} and can take parameters and return values. It is possible to use Lambda expressions wherever a function type is expected.
The full syntax includes the parameter names, an arrow ->, and the body of the function. For example:

two integers are taken and their sum is returned through the lamda expression.
```kotlin 
val sum = { a: Int, b: Int -> a + b }
```
A Higher-order function is able to either take another function as paramter and/or to return a function. This enables functional programming patterns (Examples for these are: map and filter).
Example:
```kotlin 
val numbers = listOf(1, 2, 3)
val numbersDouble = numbers.map { it * 2 }// <- Lamda expression
```
Storing a function in a variable allows for: Reusability, Flexibilty and Encapsulation.
</span>

### Provide a solution for the following number guessing game inside `App.kt`. (3 points)

## Number Guessing Game in Kotlin
The game is a simple number guessing game. The task is to generate a random, max 9-digit, number. The number must **not contain repeating digits**. Valid digits are 1-9.
Ask the user to guess the max 9-digit number. The game is finished when the user guesses the correct digits in the correct order.
In each round, the user gets feedback about the number of correct digits and the number of correct digits in the correct position.
The output should be in the format "n:m", where "n" is the number of digits guessed correctly regardless of their position, 
and "m" is the number of digits guessed correctly at their correct position. Here are some examples:

This example shows the game flow with 4-digits to guess (the default argument)

Generated number: 8576
-	User input: 1234, Output: 0:0
-	User input: 5678, Output: 4:1
-	User input: 5555, Output: 1:1
-	User input: 3586, Output: 3:2
-	User input: 8576, Output: 4:4 -> user wins

Take a look into the provided code structure in `src/main/kotlin/App.kt`. Implement the following methods (lambda expressions):
- _playNumberGame(digitsToGuess: Int = 4)_ (1 point): The main game loop that handles user input and game state. Make use of _generateRandomNonRepeatingNumber_ and _checkUserInputAgainstGeneratedNumber_ here. This function also utilizes a default argument 
- _generateRandomNonRepeatingNumber_ (1 point): A lambda expression that generates a random number with non-repeating digits of a specified length.
- _checkUserInputAgainstGeneratedNumber_ (1 point): A lambda expression that compares the user's input against the generated number and provides feedback.

``CompareResult.kt`` This class is a data structure which helps with bundling the result of the comparison of the user input and the generated number. Look at the toSting() and use it in your output.

Run the project with `./gradlew run` and test your implementation with the provided tests in `src/test/kotlin/AppTest.kt` with `./gradlew test`.

# Project Structure
The project is structured into two main Kotlin files:

**App.kt**: Contains the main game logic and functions.

**AppTest.kt**: Contains unit tests for the various functions in App.kt.

