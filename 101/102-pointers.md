# Pointers 

In Go (Golang), the * and & operators are used for working with pointers.

### 1. & (Address-of Operator)
The & operator is used to get the memory address of a variable.
It creates a pointer to the variable.

```
package main

import "fmt"

func main() {
    x := 10
    p := &x // p is a pointer to x

    fmt.Println("Value of x:", x)
    fmt.Println("Memory address of x:", &x)
    fmt.Println("Value of p (Address of x):", p)
}
```

### 2. * (Dereference Operator)
The * operator is used to dereference a pointer (i.e., access the value stored at the memory address).
It is also used to declare a pointer type.


```
package main

import "fmt"

func main() {
    x := 10
    p := &x // Pointer to x

    fmt.Println("Value of x:", x)
    fmt.Println("Value stored at pointer p:", *p) // Dereferencing pointer

    *p = 20 // Changing value at address
    fmt.Println("New value of x:", x) // x is now 20
}
```
