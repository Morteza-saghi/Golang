## Loops



### 1. range-based
this kind of loops are used to iterate over collections like slices, arrays, maps, and channels.

the syntax

```
for i , v := range v {
// code block
}
```

- i → The index (or key, if iterating over a map).
- v → The value at that index (or the value associated with the key in a map).
- v → The collection being iterated over.


#### Example 1: Iterating Over a Slice
```
package main

import "fmt"

func main() {
    numbers := []int{10, 20, 30, 40}

    for i, v := range numbers {
        fmt.Printf("Index: %d, Value: %d\n", i, v)
    }
}

```

Output:

```
Index: 0, Value: 10
Index: 1, Value: 20
Index: 2, Value: 30
Index: 3, Value: 40
```

#### ps: if any of them set to _ means we dont need that





#### Example: Iterating Over a String (Rune by Rune)

```
package main

import "fmt"

func main() {
    str := "hello"

    for i, v := range str {
        fmt.Printf("Index: %d, Character: %c\n", i, v)
    }
}
```

Output:

```
Index: 0, Character: h
Index: 1, Character: e
Index: 2, Character: l
Index: 3, Character: l
Index: 4, Character: o
```
