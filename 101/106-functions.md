# Guide to Functions in Golang

Functions are fundamental building blocks in Golang that allow code reuse, modularization, and better readability. This guide covers different types of functions in Go with examples.

### 1. Basic Function (Without Parameters & Return Value)
A simple function that performs an action without taking inputs or returning values.

```go
package main
import "fmt"

func greet() {
    fmt.Println("Hello, Golang!")
}

func main() {
    greet()
}
```

### 2. Function with Parameters
Functions can accept parameters to make them more dynamic.

```
func add(a int, b int) {
    fmt.Println("Sum:", a+b)
}

func main() {
    add(5, 3)
}
```

### 3. Function with Return Value
Functions can return values to the caller.

```
func multiply(a int, b int) int {
    return a * b
}

func main() {
    result := multiply(4, 5)
    fmt.Println("Product:", result)
}
```

### 4. Function with Multiple Return Values
Go allows functions to return multiple values.

```
func divide(a int, b int) (int, int) {
    quotient := a / b
    remainder := a % b
    return quotient, remainder
}

func main() {
    q, r := divide(10, 3)
    fmt.Println("Quotient:", q, "Remainder:", r)
}
```

### 5. Named Return Values
Named return values can improve readability by specifying return variable names.

```
func rectangleArea(length, width int) (area int) {
    area = length * width
    return // No need to explicitly return variable as it is named
}

func main() {
    fmt.Println("Area:", rectangleArea(5, 6))
}
```

### 6. Variadic Functions
Functions can accept a variable number of arguments.

```
func sum(numbers ...int) int {
    total := 0
    for _, num := range numbers {
        total += num
    }
    return total
}

func main() {
    fmt.Println("Total:", sum(1, 2, 3, 4, 5))
}
```

### 7. Anonymous Functions
Functions without a name, useful for quick inline execution.

```
func main() {
    func(message string) {
        fmt.Println(message)
    }("Hello from an anonymous function!")
}
```

### 8. Function as a Value
Functions can be assigned to variables and passed as arguments.

```
func square(n int) int {
    return n * n
}

func main() {
    var operation func(int) int = square
    fmt.Println("Square of 4:", operation(4))
}
```

### 9. Higher-Order Functions (Passing Functions as Arguments)
Functions can take other functions as arguments.

```
func applyOperation(x int, fn func(int) int) int {
    return fn(x)
}

func double(n int) int {
    return n * 2
}

func main() {
    fmt.Println("Double of 5:", applyOperation(5, double))
}
```


### 10. Closures
A closure is a function that captures variables from its surrounding scope.

```
func incrementer() func() int {
    count := 0
    return func() int {
        count++
        return count
    }
}

func main() {
    next := incrementer()
    fmt.Println(next()) // Output: 1
    fmt.Println(next()) // Output: 2
}
```

### 11. Defer in Functions
defer delays execution of a function until the surrounding function returns.

```
func main() {
    defer fmt.Println("Deferred execution")
    fmt.Println("Regular execution")
}
```


### 12. Recursive Functions
A function that calls itself to solve a problem.

```
func factorial(n int) int {
    if n == 0 {
        return 1
    }
    return n * factorial(n-1)
}

func main() {
    fmt.Println("Factorial of 5:", factorial(5))
}
```

