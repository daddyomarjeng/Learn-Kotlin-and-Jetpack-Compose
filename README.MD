
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

