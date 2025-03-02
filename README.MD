
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

---

Awesome! 🚀 Now, let's dive into **advanced OOP concepts in Kotlin**:

1️⃣ **Abstract Classes & Methods**  
2️⃣ **Interfaces**  
3️⃣ **Data Classes**  
4️⃣ **Sealed Classes**

---

## **1️⃣ Abstract Classes & Methods**
Abstract classes are **partially implemented** classes that **cannot be instantiated** directly. They are meant to be **inherited**.

### **🔹 Example: Abstract Class with Abstract Method**
```kotlin
abstract class Animal(val name: String) {
    abstract fun makeSound() // Abstract method (no implementation)
    
    fun sleep() { // Regular method
        println("$name is sleeping")
    }
}

class Dog(name: String) : Animal(name) {
    override fun makeSound() { // Providing implementation
        println("$name barks: Woof woof!")
    }
}

fun main() {
    val dog = Dog("Buddy")
    dog.makeSound() // Buddy barks: Woof woof!
    dog.sleep()     // Buddy is sleeping
}
```
💡 **Key Points:**  
✔ `abstract class` cannot be instantiated directly.  
✔ `abstract fun` must be implemented in subclasses.  
✔ Can also have **regular functions** (`sleep()`).

---

## **2️⃣ Interfaces in Kotlin**
An **interface** is like an abstract class, but:  
✔ It **cannot store state** (no properties with values).  
✔ A class can **implement multiple interfaces** (unlike single inheritance).

### **🔹 Example: Using Interfaces**
```kotlin
interface Movable {
    fun move() // No implementation
}

interface Speakable {
    fun speak() {
        println("Speaking...")
    }
}

class Robot : Movable, Speakable { // Implementing multiple interfaces
    override fun move() {
        println("Robot is moving")
    }
}

fun main() {
    val r2d2 = Robot()
    r2d2.move()   // Robot is moving
    r2d2.speak()  // Speaking...
}
```
💡 **Key Points:**  
✔ Interfaces can have **default method implementations** (`speak()`).  
✔ A class can **implement multiple interfaces** (unlike abstract classes).

---

## **3️⃣ Data Classes (For Storing Data)**
Kotlin provides **data classes** to handle **immutable objects** with built-in functions (`toString()`, `copy()`, `equals()`, etc.).

### **🔹 Example: Data Class**
```kotlin
data class User(val name: String, val age: Int)

fun main() {
    val user1 = User("Omar", 25)
    val user2 = user1.copy(age = 26) // Creates a new object with modified age

    println(user1) // User(name=Omar, age=25)
    println(user2) // User(name=Omar, age=26)
}
```
💡 **Key Points:**  
✔ `copy()` creates a modified clone.  
✔ Automatically generates **`toString()`, `equals()`, and `hashCode()`**.  
✔ Best for **models, DTOs, and API responses**.

---

## **4️⃣ Sealed Classes (For Restricted Inheritance)**
Sealed classes restrict which classes can **inherit** from them. This is useful in **state management and enums**.

### **🔹 Example: Sealed Class for State Management**
```kotlin
sealed class Result {
    class Success(val data: String) : Result()
    class Error(val message: String) : Result()
    object Loading : Result()
}

fun handleResult(result: Result) {
    when (result) {
        is Result.Success -> println("Success: ${result.data}")
        is Result.Error -> println("Error: ${result.message}")
        is Result.Loading -> println("Loading...")
    }
}

fun main() {
    handleResult(Result.Success("Data loaded successfully"))
    handleResult(Result.Error("Something went wrong"))
    handleResult(Result.Loading)
}
```
💡 **Key Points:**  
✔ `sealed class` ensures **only predefined types** (like `Success`, `Error`, `Loading`) can extend it.  
✔ Useful for **managing states** in applications (e.g., API responses).

---

## **🔥 Summary**
| Feature        | Abstract Class | Interface | Data Class | Sealed Class |
|---------------|---------------|-----------|------------|--------------|
| Can have methods with implementation | ✅ | ✅ | ✅ | ✅ |
| Can have abstract methods | ✅ | ✅ | ❌ | ❌ |
| Can store state (variables with values) | ✅ | ❌ | ✅ | ✅ |
| Multiple inheritance | ❌ | ✅ | ❌ | ❌ |
| Used for | **Base classes** | **Common behavior** | **Data storage** | **Restricted hierarchy** |

---

## **📝 Mini Task (Try This)**
### **Task:**
1. **Create an abstract class** `Vehicle` with:
   - Property: `name: String`
   - Abstract function `move()`
2. **Create two subclasses**:
   - `Car` that prints `"Car is driving"`
   - `Bicycle` that prints `"Bicycle is pedaling"`
3. **Test them in `main()`**.

```kotlin
abstract class Vehicle(val name: String) {
    abstract fun move()
}

class Car(name: String) : Vehicle(name) {
    override fun move() {
        println("$name is driving on the road 🚗💨")
    }
}

class Bicycle(name: String) : Vehicle(name) {
    override fun move() {
        println("$name is pedaling on the track 🚴‍♂️")
    }
}

fun main() {
    val car = Car("Toyota")
    val bicycle = Bicycle("Homar")

    car.move()      // Toyota is driving on the road 🚗💨
    bicycle.move()  // Homar is pedaling on the track 🚴‍♂️
}
```

---

## **1️⃣ Understanding Interfaces in Kotlin**
An **interface** is like an abstract class but with a few key differences:

✅ **Cannot store state** (no instance variables with values)  
✅ **Can have abstract and non-abstract methods**  
✅ **Supports multiple inheritance** (a class can implement multiple interfaces)

---

### **🔹 Example: Creating & Implementing an Interface**
```kotlin
interface Movable {
    fun move() // Abstract function (no implementation)
}

class Car : Movable {
    override fun move() {
        println("Car is driving on the road 🚗💨")
    }
}

fun main() {
    val myCar = Car()
    myCar.move() // Output: Car is driving on the road 🚗💨
}
```
✔ The `Car` class implements the `Movable` interface and **must** override `move()`.

---

## **2️⃣ Interfaces with Default Methods**
Kotlin interfaces **can have default method implementations**, unlike Java.

### **🔹 Example: Default Implementation**
```kotlin
interface Movable {
    fun move() {
        println("Moving...") // Default implementation
    }
}

class Bike : Movable // No need to override `move()`, it will use the default

fun main() {
    val bike = Bike()
    bike.move() // Output: Moving...
}
```
✔ If `Bike` doesn’t override `move()`, it **uses the default method** from `Movable`.

---

## **3️⃣ Multiple Interfaces in Kotlin**
A **class can implement multiple interfaces**, unlike single inheritance in classes.

### **🔹 Example: Implementing Multiple Interfaces**
```kotlin
interface Drivable {
    fun drive() {
        println("Driving...")
    }
}

interface Flyable {
    fun fly() {
        println("Flying...")
    }
}

class FlyingCar : Drivable, Flyable // Implements both interfaces

fun main() {
    val futureCar = FlyingCar()
    futureCar.drive() // Driving...
    futureCar.fly()   // Flying...
}
```
✔ `FlyingCar` **inherits from both** `Drivable` and `Flyable`.

---

## **4️⃣ Handling Conflicts in Multiple Interfaces**
If two interfaces have the **same function name**, the class **must explicitly override it**.

### **🔹 Example: Resolving Conflicts**
```kotlin
interface A {
    fun show() {
        println("Interface A")
    }
}

interface B {
    fun show() {
        println("Interface B")
    }
}

class C : A, B {
    override fun show() {
        super<A>.show() // Explicitly choosing A’s implementation
    }
}

fun main() {
    val obj = C()
    obj.show() // Output: Interface A
}
```
✔ `super<A>.show()` ensures that **A's `show()` method** is used.

---

## **🔥 Summary**
| Feature | Abstract Class | Interface |
|---------|--------------|-----------|
| Can have abstract methods | ✅ | ✅ |
| Can have concrete methods | ✅ | ✅ |
| Can store state (instance variables with values) | ✅ | ❌ |
| Supports multiple inheritance | ❌ | ✅ |
| Can be instantiated | ❌ | ❌ |

---

## **📝 Mini Task (Try This)**
### **Task:**
1. **Create an interface** `Swimmable` with:
   - A method `swim()` that prints `"Swimming..."`

2. **Create an interface** `Runnable` with:
   - A method `run()` that prints `"Running..."`

3. **Create a class** `Amphibian` that implements both interfaces.

4. **Test it in `main()`**.

```kotlin
interface Swimmable {
    fun swim() {
        println("Swimming... 🏊‍♂️")
    }
}

interface Runnable {
    fun run() {
        println("Running... 🏃‍♂️")
    }
}

class Amphibian : Swimmable, Runnable // No need for () unless passing constructor parameters

fun main() {
    val amphibian = Amphibian()
    amphibian.swim() // Output: Swimming... 🏊‍♂️
    amphibian.run()  // Output: Running... 🏃‍♂️
}
```

---

## **1️⃣ Data Classes – What & Why?**
A **data class** is used to **store data** efficiently. It automatically provides:  
✔ `toString()` → Prints the object neatly.  
✔ `equals()` → Compares object values (not references).  
✔ `copy()` → Creates a copy of an object.  
✔ `hashCode()` → Generates a unique hash for the object.

### **🔹 Example: Basic Data Class**
```kotlin
data class User(val name: String, val age: Int)

fun main() {
    val user1 = User("Omar", 25)
    val user2 = user1.copy(age = 26) // Creates a modified copy

    println(user1) // Output: User(name=Omar, age=25)
    println(user2) // Output: User(name=Omar, age=26)
}
```
✔ `copy()` allows modification without affecting the original object.  
✔ `toString()` prints user-friendly output.

---

## **2️⃣ Data Class with Default Values**
```kotlin
data class Product(val name: String, val price: Double, val stock: Int = 10)

fun main() {
    val item1 = Product("Laptop", 1200.0)
    println(item1) // Output: Product(name=Laptop, price=1200.0, stock=10)
}
```
✔ Default values (`stock=10`) avoid boilerplate code.

---

## **3️⃣ Sealed Classes – What & Why?**
A **sealed class** restricts which classes can inherit from it.  
✔ Useful for handling **states** in apps (e.g., API responses, UI states).  
✔ Works like an **advanced enum** with multiple data types.

---

### **🔹 Example: Sealed Class for API Response**
```kotlin
sealed class ApiResponse {
    class Success(val data: String) : ApiResponse()
    class Error(val message: String) : ApiResponse()
    object Loading : ApiResponse()
}

fun handleResponse(response: ApiResponse) {
    when (response) {
        is ApiResponse.Success -> println("Data: ${response.data}")
        is ApiResponse.Error -> println("Error: ${response.message}")
        is ApiResponse.Loading -> println("Loading...")
    }
}

fun main() {
    handleResponse(ApiResponse.Success("User data loaded"))
    handleResponse(ApiResponse.Error("Network error"))
    handleResponse(ApiResponse.Loading)
}
```
✔ `sealed class` **limits inheritance** to only predefined subclasses.  
✔ `when` ensures **all cases** are handled.

---

### **🔥 Summary**
| Feature | Data Class | Sealed Class |
|---------|-----------|-------------|
| Used for | **Storing data** | **Managing states** |
| Has `copy()`, `toString()`, etc. | ✅ | ❌ |
| Restricts inheritance | ❌ | ✅ |
| Supports multiple subclasses | ❌ | ✅ |

---

### **📝 Mini Task (Try This)**
#### **Task:**
1. **Create a data class** `Book` with:
   - Properties: `title`, `author`, `price`
2. **Create a sealed class** `Shape` with subclasses:
   - `Circle(radius: Double)`
   - `Rectangle(width: Double, height: Double)`
3. **Use `when` to print details** of each shape.

```kotlin
data class Book(val title: String, val author: String, val price: Double)

sealed class Shape {
    class Circle(val radius: Double) : Shape()
    class Rectangle(val width: Double, val height: Double) : Shape()
}

fun handleShapes(shape: Shape) {
    when (shape) {
        is Shape.Circle -> println("Shape is a Circle with Radius: ${shape.radius}")
        is Shape.Rectangle -> println("Shape is a Rectangle with Height: ${shape.height} and Width: ${shape.width}")
    }
}

fun main() {
    val book1 = Book("Things Fall Apart", "Chinua Achebe", 132.70)
    val book2 = book1.copy(author = "Daddy Omar Jeng")

    println("Book1: $book1")
    println("Book2: $book2")
    
    // ✅ Corrected String Interpolation
    println("Book2 toString(): ${book2.toString()}")
    
    // ✅ Fixed typo in "equals" comparison message
    println("Compare Books: Book1 is equal to Book2: ${book1 == book2}")
    println("Compare Books: Book1 is eual to book2: ${book2.equals(book1)}")
    
    println("Hash Code of Book2: ${book2.hashCode()}")

    // Handling shapes
    handleShapes(Shape.Circle(22.2))
    handleShapes(Shape.Rectangle(14.2, 8.0))
}

```

---

## **1️⃣ Kotlin Collections – Lists, Sets, and Maps**
Kotlin provides **immutable** and **mutable** collections:  
✔ **Immutable (`listOf`, `setOf`, `mapOf`)** – Cannot be modified  
✔ **Mutable (`mutableListOf`, `mutableSetOf`, `mutableMapOf`)** – Can be modified

---

### **🔹 Immutable List (Cannot be changed)**
```kotlin
fun main() {
    val names = listOf("Omar", "Jeng", "Daddy") 
    println(names[0]) // Output: Omar
    println(names.size) // Output: 3
}
```
✔ No `add()` or `remove()`, since it's **immutable**.

---

### **🔹 Mutable List (Can be changed)**
```kotlin
fun main() {
    val names = mutableListOf("Omar", "Jeng", "Daddy")
    names.add("New Name") // Adding an element
    names.remove("Jeng")  // Removing an element
    println(names) // Output: [Omar, Daddy, New Name]
}
```
✔ `mutableListOf` allows adding/removing elements.

---

### **🔹 Immutable Set (No duplicates, unordered)**
```kotlin
fun main() {
    val uniqueNumbers = setOf(1, 2, 3, 3, 2, 1)
    println(uniqueNumbers) // Output: [1, 2, 3] (No duplicates)
}
```

---

### **🔹 Mutable Set (Can be changed)**
```kotlin
fun main() {
    val uniqueNumbers = mutableSetOf(1, 2, 3)
    uniqueNumbers.add(4) // Adding
    uniqueNumbers.remove(2) // Removing
    println(uniqueNumbers) // Output: [1, 3, 4]
}
```
✔ **No duplicate values** in a `Set`.

---

### **🔹 Map (Key-Value Pairs)**
```kotlin
fun main() {
    val user = mapOf("name" to "Omar", "age" to 25)
    println(user["name"]) // Output: Omar
}
```

---

## **2️⃣ Higher-Order Functions (Functional Programming)**
Higher-order functions **take functions as parameters** or **return functions**.

---

### **🔹 `forEach` – Loop Through a List**
```kotlin
fun main() {
    val numbers = listOf(1, 2, 3)
    numbers.forEach { println(it * 2) } // Output: 2, 4, 6
}
```

---

### **🔹 `map` – Transform List**
```kotlin
fun main() {
    val numbers = listOf(1, 2, 3)
    val doubled = numbers.map { it * 2 }
    println(doubled) // Output: [2, 4, 6]
}
```
✔ **`map` transforms** each element in a list.

---

### **🔹 `filter` – Get Specific Elements**
```kotlin
fun main() {
    val numbers = listOf(1, 2, 3, 4, 5)
    val evenNumbers = numbers.filter { it % 2 == 0 }
    println(evenNumbers) // Output: [2, 4]
}
```
✔ `filter` **keeps only the elements that match the condition**.

---

### **🔹 `reduce` – Accumulate Values**
```kotlin
fun main() {
    val numbers = listOf(1, 2, 3, 4)
    val sum = numbers.reduce { acc, num -> acc + num }
    println(sum) // Output: 10
}
```
✔ `reduce` **accumulates a value step by step**.

---

### **📝 Mini Task (Try This)**
#### **Task:**
1. Create a **mutable list** of numbers.
2. Use `map()` to multiply each number by **3**.
3. Use `filter()` to keep only numbers **greater than 10**.
4. Use `reduce()` to **sum all elements**.

```kotlin
fun main() {
   val numbers = mutableListOf(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
   
    // val multiplesOfThree = numbers.map{num-> num * 3};
   val multiplesOfThree = numbers.map { it * 3 }
   println("Numbers multiplied by 3: $multiplesOfThree")

   //  val numbersGreaterThanTen = multiplesOfThree.filter{num-> num > 10}
   val numbersGreaterThanTen = multiplesOfThree.filter { it > 10 }
   println("Numbers greater than 10: $numbersGreaterThanTen")

   val sumOfAllNumbers = numbersGreaterThanTen.reduce { acc, num -> acc + num }
   println("Sum of all numbers: $sumOfAllNumbers")
}

```

---

# **1️⃣ Encapsulation in Kotlin**
Encapsulation is about **restricting access** to data using **visibility modifiers**:  
✔ `private` → Only accessible within the same class  
✔ `protected` → Accessible in the same class & subclasses  
✔ `public` (default) → Accessible from anywhere  
✔ `internal` → Accessible within the same module

---

### **🔹 Example: Encapsulation with Getters & Setters**
```kotlin
class BankAccount(private var balance: Double) {
    fun deposit(amount: Double) {
        if (amount > 0) {
            balance += amount
            println("Deposited: $$amount, New Balance: $$balance")
        }
    }

    fun withdraw(amount: Double) {
        if (amount > 0 && amount <= balance) {
            balance -= amount
            println("Withdrew: $$amount, Remaining Balance: $$balance")
        } else {
            println("Insufficient funds or invalid amount!")
        }
    }
}

fun main() {
    val account = BankAccount(100.0)
    account.deposit(50.0)
    account.withdraw(30.0)
}
```
✔ **Encapsulated `balance`** (it can’t be directly modified).  
✔ **Controlled access using `deposit()` and `withdraw()` methods.**

---

# **2️⃣ Inheritance & Method Overriding**
Inheritance allows a **subclass** to reuse or override features from a **parent class**.

---

### **🔹 Example: Basic Inheritance**
```kotlin
open class Animal {
    open fun makeSound() {
        println("Some generic animal sound")
    }
}

class Dog : Animal() {
    override fun makeSound() {
        println("Woof! Woof!")
    }
}

fun main() {
    val genericAnimal = Animal()
    val myDog = Dog()

    genericAnimal.makeSound() // Output: Some generic animal sound
    myDog.makeSound() // Output: Woof! Woof!
}
```
✔ **`open` keyword** makes `Animal` **inheritable**.  
✔ **`override` keyword** allows `Dog` to change `makeSound()`.

---

# **3️⃣ Companion Objects (Static Methods)**
Kotlin **does not have `static` keywords**, but we can use **companion objects** instead.

---

### **🔹 Example: Companion Object**
```kotlin
class MathUtil {
    companion object {
        fun add(a: Int, b: Int): Int {
            return a + b
        }
    }
}

fun main() {
    println(MathUtil.add(5, 3)) // Output: 8
}
```
✔ `companion object` allows calling `add()` **without creating an instance**.  
✔ Equivalent to **static methods** in Java.

---

## **📝 Mini Task (Try This)**
### **Task:**
1. **Create a class `Car`** with:
   - A **private** property `speed`
   - Methods `accelerate()` and `brake()`
2. **Create a subclass `SportsCar`** that:
   - Overrides `accelerate()` to increase speed **faster**
3. **Add a `companion object`** with a method `carInfo()`

```kotlin
open class Car(private var speed: Double) {
    open fun accelerate() {
        speed += 10
        println("Accelerating... Speed is now $speed km/h")
    }

    fun brake() {
        speed -= 5
        if (speed < 0) speed = 0
        println("Braking... Speed is now $speed km/h")
    }

    companion object {
        fun carInfo(name: String, brand: String, price: Double) {
            println("Car Name: $name, Car Brand: $brand, Car Price: $$price")
        }
    }
}

class SportsCar(speed: Double) : Car(speed) {
    override fun accelerate() {
        super.accelerate() // Call the parent method
        println("Sports Car accelerating even faster! 🚀")
    }
}

fun main() {
    val car = SportsCar(32.4)
    car.accelerate()
    car.brake()
    Car.carInfo("Rav4", "Toyota", 3200.0)
}
```
### **🚀 1️⃣ Kotlin Lambdas & Higher-Order Functions**

A **lambda function** is an **anonymous function** (a function without a name).

---

### **🔹 Basic Lambda Expression**
```kotlin
val sum = { a: Int, b: Int -> a + b }

fun main() {
    println(sum(5, 3)) // Output: 8
}
```
✔ `{ a: Int, b: Int -> a + b }` is a **lambda expression**.  
✔ It is assigned to `val sum` and can be **called like a function**.

---

### **🔹 Passing Lambda as Function Parameter**
```kotlin
fun operateOnNumbers(a: Int, b: Int, operation: (Int, Int) -> Int): Int {
    return operation(a, b)
}

fun main() {
    val result = operateOnNumbers(4, 2) { x, y -> x * y }
    println(result) // Output: 8
}
```
✔ The function **takes a lambda as a parameter**.  
✔ `operation: (Int, Int) -> Int` means it expects a function that **takes two `Int`s and returns an `Int`**.

---

### **🔹 `it` Keyword (Single Parameter Lambda)**
```kotlin
val square: (Int) -> Int = { it * it }

fun main() {
    println(square(4)) // Output: 16
}
```
✔ If a **lambda has only one parameter**, we can use **`it`** instead of explicitly naming it.

---

### **🔹 `filter`, `map`, `reduce` with Lambdas**
```kotlin
fun main() {
    val numbers = listOf(1, 2, 3, 4, 5, 6)

    val evens = numbers.filter { it % 2 == 0 }
    println(evens) // Output: [2, 4, 6]

    val squared = numbers.map { it * it }
    println(squared) // Output: [1, 4, 9, 16, 25, 36]

    val sum = numbers.reduce { acc, num -> acc + num }
    println(sum) // Output: 21
}
```
✔ `filter` → **keeps elements matching a condition**.  
✔ `map` → **transforms each element**.  
✔ `reduce` → **accumulates elements**.

---


## **🚀 2️⃣ Kotlin Coroutines (Asynchronous Programming)**
A **coroutine** is like a lightweight thread for handling async tasks **without blocking the main thread**.

### **🔹 Launching a Coroutine**
```kotlin
import kotlinx.coroutines.*

fun main() = runBlocking {
    launch {
        delay(1000L) // Simulates network request
        println("Hello from coroutine!")
    }
    println("Main thread running...")
}
```
✔ `launch {}` creates a new coroutine.  
✔ `delay(1000L)` pauses the coroutine **without blocking the main thread**.  
✔ `runBlocking` keeps the **main function alive** until coroutines complete.

---

### **🔹 Using `async` for Parallel Execution**
```kotlin
import kotlinx.coroutines.*

fun main() = runBlocking {
    val first = async { getData1() }
    val second = async { getData2() }
    
    println("Result: ${first.await() + second.await()}")
}

suspend fun getData1(): Int {
    delay(1000L)
    return 10
}

suspend fun getData2(): Int {
    delay(1000L)
    return 20
}
```
✔ `async` runs **multiple coroutines in parallel**.  
✔ `await()` waits for the result **without blocking the thread**.  
✔ `suspend fun` → A function that can **pause & resume execution**.

---

### **📝 Mini Task (Try This)**
### **Task:**
1. **Create two `suspend fun` functions** that return a number after a delay.
2. **Use `async {}`** to call both functions **in parallel**.
3. **Print the sum of both results**.

```kotlin
import kotlinx.coroutines.*
import kotlin.system.measureTimeMillis

suspend fun number1(): Int {
    delay(1000L)
    return 20
}

suspend fun number2(): Int {
    delay(400L)
    return 10
}

fun main() = runBlocking {
    val timeTaken = measureTimeMillis {
        val num1 = async { number1() }
        val num2 = async { number2() }
        val sum = num1.await() + num2.await()
        println("Sum: $sum")
    }
    println("Time taken: $timeTaken ms")
}
```

# 🚀 **Kotlin Flow: Reactive Programming with Cold Streams**

**Kotlin Flow** is a powerful tool for handling **real-time, asynchronous data streams** efficiently.

---

## **1️⃣ What is Kotlin Flow?**
- **Similar to LiveData/RxJava**, but part of **Kotlin Coroutines**.
- **Cold stream** → It **doesn’t start emitting data until it is collected**.
- **Asynchronous & Reactive** → Perfect for handling **network requests, database updates, sensor data, etc.**

---

## **2️⃣ Basic Flow Example**
```kotlin
import kotlinx.coroutines.*
import kotlinx.coroutines.flow.*

fun simpleFlow(): Flow<Int> = flow {
    for (i in 1..5) {
        delay(500L) // Simulates async work
        emit(i) // Emit values one by one
    }
}

fun main() = runBlocking {
    simpleFlow().collect { value ->
        println("Received: $value")
    }
}
```

### **🔹 Explanation**
✔ `flow {}` → Defines a **Flow** that emits numbers from `1` to `5`.  
✔ `emit(value)` → Sends values **one by one**.  
✔ `collect {}` → Collects (subscribes to) the emitted values.  
✔ **Delays are handled asynchronously** using coroutines.

---

## **3️⃣ Flow is Cold (Starts When Collected)**
Unlike a coroutine that starts immediately, a Flow **only starts when a collector is present**.

```kotlin
fun main() = runBlocking {
    val numbersFlow = simpleFlow() // Flow is defined but not executed

    delay(2000L) // Wait for 2 seconds before collecting

    numbersFlow.collect { value -> println("Received: $value") } // Flow starts now
}
```
✔ The Flow **doesn’t run** until `.collect()` is called.

---

## **4️⃣ Operators in Flow (`map`, `filter`, `take`)**
Just like collections (`List`), Flow supports **operators** to transform data.

```kotlin
fun main() = runBlocking {
    simpleFlow()
        .map { it * 2 }  // Double the values
        .filter { it > 5 } // Keep values > 5
        .take(2) // Take only the first 2 results
        .collect { println("Processed: $it") }
}
```
✔ `map {}` → **Transforms** each item.  
✔ `filter {}` → **Filters** items.  
✔ `take(n)` → **Takes only `n` values** from the Flow.

---

## **5️⃣ Flow vs Suspend Function**
| Feature        | Flow | Suspend Function |
|---------------|------|-----------------|
| **Returns** | **Multiple values over time** | **Single value** |
| **Execution** | **Cold (Runs only when collected)** | **Runs immediately** |
| **Best for** | **Real-time data, streaming** | **Single network/database request** |

---

### **🚀 3️⃣ Kotlin Flow (Cold Streams & Real-Time Data)**
Kotlin **Flow** is designed for **reactive programming**, making it perfect for **handling streams of data asynchronously**.

Unlike **suspend functions**, which return **a single value**, **Flow** can emit **multiple values over time**.

---

## **🔹 Basic Flow Example**
```kotlin
import kotlinx.coroutines.*
import kotlinx.coroutines.flow.*

fun main() = runBlocking {
    simpleFlow().collect { value ->
        println("Received: $value")
    }
}

fun simpleFlow(): Flow<Int> = flow {
    for (i in 1..5) {
        delay(500) // Simulate a slow operation
        emit(i) // Emit values one by one
    }
}
```

✔ **Flow produces multiple values over time** (like a stream).  
✔ **`collect {}`** listens for new values.  
✔ **`emit(value)`** sends data into the Flow.  
✔ **Cold Stream** → It only starts when there is a collector.

---

## **🔹 Flow vs. Suspend Function**
| Feature       | `suspend fun` | `Flow` |
|--------------|--------------|--------|
| Returns      | Single value | Multiple values |
| Execution    | Calls once   | Emits repeatedly |
| Usage        | One-time operation | Continuous updates (e.g., LiveData) |

---

## **🔹 Transforming Flow (`map`, `filter`)**
We can apply **functional operations** on Flow, just like with lists!

```kotlin
fun transformedFlow(): Flow<Int> = flow {
    for (i in 1..5) {
        delay(500)
        emit(i)
    }
}.map { it * 2 } // Doubles each number

fun main() = runBlocking {
    transformedFlow().collect { value ->
        println("Transformed: $value")
    }
}
```

✔ `map { it * 2 }` → **Transforms values before emitting**.  
✔ **Output:** `2, 4, 6, 8, 10`

---

## **🔹 Flow Operators: `filter()`**
We can filter Flow just like lists.

```kotlin
fun filteredFlow(): Flow<Int> = flow {
    for (i in 1..10) {
        delay(200)
        emit(i)
    }
}.filter { it % 2 == 0 } // Keeps only even numbers

fun main() = runBlocking {
    filteredFlow().collect { value ->
        println("Even Number: $value")
    }
}
```

✔ `filter { it % 2 == 0 }` → **Keeps only even numbers**.  
✔ **Output:** `2, 4, 6, 8, 10`

---

## **🔹 Flow with `buffer()` (Parallel Processing)**
Normally, **Flow is sequential**, meaning it **waits** for each operation to finish before emitting the next value.  
To **speed up processing**, we can use **`buffer()`** to collect items **asynchronously**.

```kotlin
fun bufferedFlow(): Flow<Int> = flow {
    for (i in 1..3) {
        delay(500)
        emit(i)
    }
}.buffer() // Allows parallel collection

fun main() = runBlocking {
    bufferedFlow().collect { value ->
        println("Buffered value: $value")
        delay(1000) // Simulating slow collector
    }
}
```

✔ **Without `buffer()`**: **Total time = 3 × (500ms + 1000ms) = 4.5 sec**  
✔ **With `buffer()`**: **Total time reduced to ~3 sec**

---

## **📝 Mini Task (Try This)**
### **Task:**
1. **Create a Flow** that emits numbers from **1 to 10**.
2. **Use `map()`** to square each number.
3. **Use `filter()`** to keep only numbers greater than **20**.
4. **Collect the Flow and print the values**.

```kotlin
import kotlinx.coroutines.*
import kotlinx.coroutines.flow.*

fun myFlow():Flow<Int> = flow{
	for(i in 1..10){
        delay(200);
        emit(i)
    }
}.map{it *it}.filter{it > 20}

fun main() = runBlocking {
    myFlow().collect {value -> println("Flow: ${value}")}
}
```