### 1. Arrays

**Fixed Size**: The size of an array is part of its type. Once defined, the size cannot be changed.

**Declaration**:

```
var arr [5]int // An array of 5 integers
```


```
arr := [3]string{"a", "b", "c"} // An array of 3 strings
```

- Value Type: Arrays are value types in Go. This means when you assign or pass an array to a function, a copy of the array is created. Changes to the copy do not affect the original array.

```
arr1 := [2]int{1, 2}
arr2 := arr1 // arr2 is a copy of arr1
arr2[0] = 99
fmt.Println(arr1) // [1, 2] (unchanged)
fmt.Println(arr2) // [99, 2]
```
Use Case: Arrays are useful when you need a fixed-size collection, but they are less flexible than slices.

### 2. Slices
Dynamic Size: Slices are dynamically sized and can grow or shrink as needed. They are built on top of arrays but provide more flexibility.

Declaration:

```
var slice []int // A slice of integers (initially nil)
```

or

```
slice := []string{"a", "b", "c"} // A slice of 3 strings
```

- Reference Type: Slices are reference types. When you assign or pass a slice to a function, it refers to the same underlying array. Changes to the slice affect the original data.

```
slice1 := []int{1, 2}
slice2 := slice1 // slice2 refers to the same underlying array as slice1
slice2[0] = 99
fmt.Println(slice1) // [99, 2] (changed)
fmt.Println(slice2) // [99, 2]
```

Underlying Array: A slice is a lightweight data structure that provides a "view" into an underlying array. It consists of three components:

**Pointer**: Points to the first element of the slice in the underlying array.

**Length**: The number of elements in the slice.

**Capacity**: The maximum number of elements the slice can hold without resizing the underlying array.

**Resizing**: Slices can be resized using the append function, which automatically handles the underlying array's capacity.

```
slice := []int{1, 2, 3}
slice = append(slice, 4) // Append a new element
fmt.Println(slice) // [1, 2, 3, 4]
```

Use Case: Slices are the preferred way to work with collections in Go because of their flexibility and dynamic nature.
