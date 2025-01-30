# Variable Declaration in Go (Golang)

Golang, being a statically typed language, requires variables to have a declared type or be initialized in a way that the type is inferred. Understanding how to declare and use variables in Go is crucial to writing clean, effective code.

---


## 1. Basic Variable Declaration

In Go, the `var` keyword is used to declare a variable. The basic syntax follows this structure:


```
var <name> <type>
```

#### Here is an example:

```
var name string
var age int
```

In the above example, the name variable is declared as a string, and age is declared as an int. These variables are initialized to their zero values (more on zero values later).
Variable Initialization

You can also initialize a variable at the time of declaration:

```
var name string = "John"
var age int = 30
```

Go can infer the type if a value is provided, so the following would work as well:

```
var name = "John" // Go infers that this is a string
var age = 30      // Go infers that this is an int
```

## 2. Short Variable Declaration

Go provides a shorthand for variable declaration using the := operator. This is commonly used inside functions.

```
name := "Alice"
age := 25
```

This approach is concise, and Go infers the variable type based on the assigned value. However, note that this shorthand cannot be used outside of a function body.

---

## 3. Multiple Variable Declaration

Go allows you to declare multiple variables at once. This can be done in two ways: either in a single line or using a block.
Single Line Declaration

```
var x, y, z int
```


Here, x, y, and z are all declared as integers.

#### Block Declaration

You can also declare variables using a block for better readability:

```
var (
    name   string
    age    int
    height float64
)

```

This is especially useful when dealing with multiple variables of different types.
Simultaneous Assignment

#### simultaneous assignment of variables:

```
x, y := 5, 10
```

This assigns x to 5 and y to 10 in one line.

---

## 4. Zero Values

If a variable is declared without an initial value, it takes on the zero value for its type. These are the default values:

```
0 for numeric types (e.g., int, float64)

false for bool

"" (empty string) for string

nil for pointers, slices, maps, channels, interfaces, and function types

```

Example:

```
var number int       // number is 0
var isActive bool    // isActive is false
var message string   // message is ""
```

---

## 5. Constants

In Go, you can declare constants using the const keyword. Constants cannot be changed once declared and must be initialized at the time of declaration.

```
const Pi = 3.14
const Greeting = "Hello, World!"
```

### Typed and Untyped Constants

Constants can be either typed or untyped. Untyped constants are more flexible because they can be assigned to different types.

```
const A = 42         // Untyped constant
const B int = 42     // Typed constant
```

In general, prefer untyped constants unless you need a specific type.

---


## 6. Best Practices

Here are some best practices to follow when working with variables in Go:

- Use short declaration (:=) when inside functions: It keeps the code clean and readable.

```
name := "Bob"
```

Prefer block declarations for multiple variables: It enhances readability, especially with multiple types.

```
var (
    name   string
    age    int
    score  float64
)

```

Avoid using global variables unless necessary: Use function-level variables as much as possible to avoid unwanted side effects.

```

func example() {
    // local variable
    localVar := 10
}


```

Keep variable names meaningful: Avoid single-letter names except for short loops or index variables (i, j, etc.).

Use constants where values don’t change: If a value is never supposed to change, always declare it as a constant.

```
const MaxItems = 100
```
## Value Type vs Reference Type

### 1️⃣ Value Type
A value type stores the actual value in memory. When you assign a value type variable to another variable, a copy of the value is made.

🔹 Characteristics of Value Types
✔️ Stored in the stack (fast access).
✔️ Each variable has its own copy of data.
✔️ Changes to one variable do not affect the original.
✔️ Generally used for small, simple data types.

🔸 Examples of Value Types
Go: int, float64, bool, string, array, struct (non-pointer).

Example (Value Type Behavior)
```
package main
import "fmt"

func main() {
    a := 10
    b := a  // A copy of a is assigned to b

    b = 20  // Changing b does not affect a
    fmt.Println(a) // Output: 10
    fmt.Println(b) // Output: 20
}
```



### 2️⃣ Reference Type
A reference type stores a memory address (reference) instead of the actual value. When assigned to another variable, both variables point to the same memory location.

🔹 Characteristics of Reference Types
✔️ Stored in the heap (slower but dynamic).
✔️ Multiple variables can reference the same data.
✔️ Changes to one variable affect all references.
✔️ Used for complex data structures like slices, maps, pointers, and objects.

🔸 Examples of Reference Types
Go: slice, map, pointer, channel, interface.


Example (Reference Type Behavior)

```
package main
import "fmt"

func main() {
    a := []int{1, 2, 3}
    b := a  // Both point to the same memory location

    b[0] = 100  // Changing b affects a
    fmt.Println(a) // Output: [100, 2, 3]
    fmt.Println(b) // Output: [100, 2, 3]
}
```


