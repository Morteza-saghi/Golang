# Working with Maps in Golang

## Introduction
Maps in Golang are built-in data structures that provide key-value storage. They are similar to hash tables or dictionaries in other programming languages. Maps allow fast lookups, additions, and deletions of elements.

## Creating a Map
A map in Golang is declared using the `make` function or by using map literals. The syntax is:

```go
exampleMap := make(map[int]struct {
	firstName string
	lastName  string
	age       int
})
```

#### Here, exampleMap is a map where keys are of type int, and values are anonymous structs.

### Adding Elements to a Map
You can add elements to a map using the assignment operator =:

```
exampleMap[1] = struct {
	firstName string
	lastName  string
	age       int
}{firstName: "John", lastName: "Doe", age: 30}
fmt.Println(exampleMap)

```

### Updating Elements in a Map
To update an existing element, simply assign a new value to the existing key:

```
exampleMap[1] = struct {
	firstName string
	lastName  string
	age       int
}{firstName: "Jane", lastName: "Smith", age: 28}
fmt.Println(exampleMap)
```


### Deleting Elements from a Map
You can remove a key-value pair from the map using the delete function:

```
delete(exampleMap, 1)
fmt.Println(exampleMap)
```

If the key 1 exists in exampleMap, it will be removed. If the key is not found, delete does nothing.

---


### Accessing Elements in a Map
To retrieve a value from a map, use the key:

```
fmt.Println(exampleMap[1])
```
If the key exists, the corresponding value is returned. If the key does not exist, the zero value of the value type is returned. In this case, an empty anonymous struct will be returned.




