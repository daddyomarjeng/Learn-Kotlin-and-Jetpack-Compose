
## **🚀 Kotlin Fundamentals: Lesson 1 – Basics & Variables**

### **1️⃣ Hello Kotlin!**
First, let’s write a simple **Hello World** program in Kotlin.  
If you have **Android Studio**, you can use the **Kotlin Playground** inside it. Alternatively, try [Kotlin Playground Online](https://play.kotlinlang.org/).

```kotlin
fun main() {
    println("Hello, Kotlin!")
}
```
- `fun main()` → This is the main function, just like `function` in JS.
- `println()` → Prints output to the console.

---

### **2️⃣ Variables & Data Types**
In Kotlin, variables are **strongly typed** and can be **mutable (`var`) or immutable (`val`)**.

#### **🔹 Immutable (`val`) – Like `const` in JS**
Once assigned, the value **cannot** be changed.
```kotlin
val name: String = "Omar"
val age: Int = 25
// name = "Jeng" ❌ (Error: Val cannot be reassigned)
```

#### **🔹 Mutable (`var`) – Like `let` in JS**
You **can** change the value later.
```kotlin
var country = "Gambia"
country = "Senegal" // ✅ Allowed
```

#### **💡 Kotlin has Type Inference**
You **don’t** always need to specify the type:
```kotlin
val city = "Banjul" // Kotlin knows it's a String
val population = 400_000 // Kotlin knows it's an Int
```

#### **🔹 Primitive Data Types**
| Kotlin Type  | JS Equivalent | Example  |
|-------------|--------------|----------|
| `Int`       | `Number`     | `val x: Int = 10` |
| `Double`    | `Number`     | `val pi: Double = 3.14` |
| `Boolean`   | `Boolean`    | `val isDev: Boolean = true` |
| `String`    | `String`     | `val name: String = "Omar"` |

---

### **3️⃣ String Interpolation & Concatenation**
#### **🔹 Using `$` for Interpolation (Like Template Literals in JS)**
```kotlin
val firstName = "Omar"
val lastName = "Jeng"
println("My name is $firstName $lastName")
```

#### **🔹 Using `${}` for Complex Expressions**
```kotlin
val num1 = 10
val num2 = 20
println("Sum: ${num1 + num2}") // Output: Sum: 30
```

---

### **4️⃣ Null Safety (Important in Kotlin)**
Kotlin **does not allow null values** by default to avoid `NullPointerException` (NPE).

#### **🔹 Nullable Variables (`?`)**
Use `?` to declare nullable types:
```kotlin
var nullableName: String? = "Omar"
nullableName = null // ✅ Allowed
```

#### **🔹 Safe Call Operator (`?.`)**
Prevents crashes when accessing nullable variables.
```kotlin
println(nullableName?.length) // Prints length or null
```

#### **🔹 Elvis Operator (`?:`)**
Provides a **default value** if the variable is null.
```kotlin
val result = nullableName?.length ?: 0 // If null, use 0
println("Name length: $result")
```

---

## **📝 Mini Task (Try This)**
Write a Kotlin program that:
1. Declares a `val` for your name and a `var` for your favorite programming language.
2. Prints a sentence using string interpolation.
3. Declares a nullable variable and uses the **Elvis operator (`?:`)** to print a fallback value.

```kotlin
val name = "Daddy Omar Jeng"
var favoriteProgrammingLanguage: String? = "Javascript" // Nullable

println("My name is $name, and my favorite programming language is $favoriteProgrammingLanguage.")

// Using Elvis operator correctly
favoriteProgrammingLanguage = null  // Simulating a null case
val secondFavorite = favoriteProgrammingLanguage ?: "Python"

println("My second favorite language is $secondFavorite")

```

---

Great! 🚀 Let’s move on to **Control Flow** in Kotlin. This includes **if statements, when expressions, and loops**, which will help us build logic in our programs.

---

## **🚀 Lesson 2: Control Flow (if, when, loops)**

### **1️⃣ If-Else Statements**
Kotlin’s `if` statement is similar to JavaScript, but it can also **return values**.

#### **🔹 Basic If-Else**
```kotlin
fun main() {
    val age = 20

    if (age >= 18) {
        println("You are an adult")
    } else {
        println("You are a minor")
    }
}
```

#### **🔹 If-Else as an Expression**
In Kotlin, `if` can **return a value** (like the ternary operator in JavaScript `condition ? value1 : value2`).
```kotlin
fun main() {
    val number = 10
    val result = if (number % 2 == 0) "Even" else "Odd"
    println("The number is $result")
}
```
---

### **2️⃣ When Expressions (Like Switch in JS)**
Kotlin replaces `switch-case` with a more powerful `when`.

#### **🔹 Basic When**
```kotlin
fun main() {
    val day = 3

    when (day) {
        1 -> println("Monday")
        2 -> println("Tuesday")
        3 -> println("Wednesday")
        else -> println("Invalid day")
    }
}
```

#### **🔹 When with Ranges & Multiple Conditions**
```kotlin
fun main() {
    val grade = 85

    when (grade) {
        in 90..100 -> println("A")
        in 80..89 -> println("B")
        in 70..79 -> println("C")
        else -> println("F")
    }
}
```
💡 **Ranges (`in 90..100`)** check if a value falls within a specific range.

---

### **3️⃣ Loops (For, While, Do-While)**
#### **🔹 For Loop (Iterating Over a Range)**
```kotlin
fun main() {
    for (i in 1..5) {
        println("Number: $i")
    }
}
```
💡 `1..5` means **from 1 to 5 (inclusive)**. If you want **exclusive**, use `until`:
```kotlin
for (i in 1 until 5) { // Stops at 4
    println(i)
}
```

#### **🔹 For Loop with Step**
```kotlin
for (i in 1..10 step 2) {
    println(i)  // Prints: 1, 3, 5, 7, 9
}
```

#### **🔹 For Loop Over a List**
```kotlin
val languages = listOf("Kotlin", "Java", "TypeScript")
for (language in languages) {
    println("I love $language")
}
```

#### **🔹 While Loop**
```kotlin
var x = 5
while (x > 0) {
    println("Countdown: $x")
    x--
}
```

#### **🔹 Do-While Loop (Runs at Least Once)**
```kotlin
var y = 0
do {
    println("This runs at least once")
    y++
} while (y < 1)
```

---

## **📝 Mini Task (Try This)**
Write a Kotlin program that:
1. Asks the user for a **number**.
2. Uses `when` to print:
    - `"Positive"` if the number is greater than 0.
    - `"Negative"` if less than 0.
    - `"Zero"` if it's exactly 0.
3. Uses a `for` loop to print all numbers from **1 to the given number**.

```kotlin
 print("Enter a number: ")
 val input = readLine() // Reads user input as a string
 val number = input?.toIntOrNull() // Converts input to Int (handling nulls)

 if (number != null) {
     // 1️⃣ Using `when` to check if it's Positive, Negative, or Zero
     when {
         number > 0 -> println("Positive")
         number < 0 -> println("Negative")
         else -> println("Zero")
     }

     // 2️⃣ Using a `for` loop to print numbers from 1 to the given number
     if (number > 0) {
         println("Numbers from 1 to $number:")
         for (i in 1..number) {
             print("$i ")
         }
     } else {
         println("No range to print since number is negative or zero.")
     }
 } else {
     println("Invalid input! Please enter a valid number.")
 }


```
---
Awesome! 🚀 Now, let's dive into **Functions & Object-Oriented Programming (OOP) in Kotlin**.

---

## **🚀 Lesson 3: Functions & OOP in Kotlin**
Functions help us organize code, and OOP allows us to structure applications using classes and objects.

---

### **1️⃣ Functions in Kotlin**
A function is a block of reusable code that performs a specific task.

#### **🔹 Basic Function**
```kotlin
fun greet() {
    println("Hello, Kotlin!")
}

fun main() {
    greet() // Calling the function
}
```

#### **🔹 Function with Parameters**
```kotlin
fun greet(name: String) {
    println("Hello, $name!")
}

fun main() {
    greet("Omar") // Output: Hello, Omar!
}
```

#### **🔹 Function with Return Value**
```kotlin
fun add(a: Int, b: Int): Int {
    return a + b
}

fun main() {
    val sum = add(5, 3)
    println("Sum: $sum") // Output: Sum: 8
}
```

#### **🔹 Single Expression Function (Short Syntax)**
```kotlin
fun multiply(a: Int, b: Int) = a * b

fun main() {
    println(multiply(4, 3)) // Output: 12
}
```

#### **🔹 Default & Named Parameters**
```kotlin
fun greet(name: String = "Guest") {
    println("Hello, $name!")
}

fun main() {
    greet()         // Output: Hello, Guest!
    greet("Omar")   // Output: Hello, Omar!
}
```

---

## **2️⃣ Object-Oriented Programming (OOP) in Kotlin**
OOP helps us structure our code using **Classes, Objects, Inheritance, and Encapsulation**.

### **🔹 Creating a Class & Object**
```kotlin
class Person(val name: String, val age: Int) {
    fun introduce() {
        println("Hi, my name is $name and I am $age years old.")
    }
}

fun main() {
    val person = Person("Omar", 25)
    person.introduce()
}
```

### **🔹 Constructors in Kotlin**
```kotlin
class Car(val brand: String, val model: String, val year: Int) {
    fun displayInfo() {
        println("$brand $model, Year: $year")
    }
}

fun main() {
    val myCar = Car("Toyota", "Camry", 2022)
    myCar.displayInfo()
}
```

### **🔹 Inheritance (Extending a Class)**
```kotlin
open class Animal(val name: String) {
    fun makeSound() {
        println("$name makes a sound")
    }
}

class Dog(name: String) : Animal(name) {
    fun bark() {
        println("$name barks: Woof woof!")
    }
}

fun main() {
    val dog = Dog("Buddy")
    dog.makeSound()
    dog.bark()
}
```
- `open` keyword allows the class to be inherited.
- `Dog` class extends `Animal` and adds a new method (`bark`).

### **🔹 Encapsulation (Using Private Variables)**
```kotlin
class BankAccount(private var balance: Double) {
    fun deposit(amount: Double) {
        balance += amount
        println("Deposited: $$amount. New Balance: $$balance")
    }

    fun getBalance(): Double {
        return balance
    }
}

fun main() {
    val account = BankAccount(1000.0)
    account.deposit(500.0)
    println("Current Balance: ${account.getBalance()}")
}
```
- `private` hides `balance` from being accessed outside the class.
- `deposit` and `getBalance` provide controlled access.

---

## **📝 Mini Task (Try This)**
1. **Create a `Student` class** with:
   - Properties: `name` (String) and `grade` (Int).
   - A function `displayInfo()` that prints: `"Student: Name, Grade: Grade"`.
2. **Inherit from `Student` to create a `CollegeStudent` class** with:
   - Additional property: `major` (String).
   - A function `showMajor()` that prints: `"Major: MajorName"`.

Perfect! 🎉 Your Kotlin OOP implementation is correct and well-structured. Just a couple of **minor improvements** for better readability:

### **✅ Suggested Improvements**
1. **Use `override` for customization**: If you want `CollegeStudent` to have a different `displayInfo()` method, you can use `open` and `override`.
2. **Use `super` to call parent class methods**.

---

```kotlin
open class Student(val name:String, val grade:String){
    fun displayInfo(){
        println("Student: $name, Grade: $grade");
    }
}
class CollegeStudent(name:String, grade:String, val major:String):Student(name, grade){
    fun showMajor(){
        println("Major: $major");
    }
}
fun main() {
 val collegeStudent = CollegeStudent("Omar Jeng", "3.9", "Information Systems");
    collegeStudent.displayInfo();
    collegeStudent.showMajor();
}
```
### **🔹 Optimized Version with `override`**
```kotlin
open class Student(val name: String, val grade: String) {
    open fun displayInfo() {
        println("Student: $name, Grade: $grade")
    }
}

class CollegeStudent(name: String, grade: String, val major: String) : Student(name, grade) {
    override fun displayInfo() {
        super.displayInfo() // Calls the parent class method
        println("Major: $major")
    }
}

fun main() {
    val collegeStudent = CollegeStudent("Omar Jeng", "3.9", "Information Systems")
    collegeStudent.displayInfo() // Now prints Major as well
}
```
### **🛠️ Changes & Benefits**
1. **Used `open fun` and `override fun`** → Allows `displayInfo()` in `CollegeStudent` to override the parent method.
2. **Used `super.displayInfo()`** → Calls the parent’s `displayInfo()` method inside the child class.
3. **Less redundant `println()` calls** → Now, `displayInfo()` automatically prints everything.

---

### **📌 Output**
```
Student: Omar Jeng, Grade: 3.9
Major: Information Systems
```

This version makes it **easier to extend** in the future. Try it out and let me know if you want to explore more advanced OOP concepts like **interfaces, data classes, or abstract classes**! 🚀