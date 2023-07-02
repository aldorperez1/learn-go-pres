+++
+++

{{% section %}}

# Working with Maps in Go


---
#### Assigning Values to a Map

```go
// Declare and initialize a map
myMap := make(map[string]int)

// Assign values to the map
myMap["apple"] = 3
myMap["banana"] = 5
```

- Declare a map using `make` and provide the key and value types.
- Assign values to the map using the key as an index.

---
 #### Runtime Error with Nil Maps

```go
// Declare a nil map
var myMap map[string]int

// Attempt to assign a value to a nil map
myMap["apple"] = 3 // Runtime error: assignment to entry in nil map
```

- Nil maps have no underlying storage and cannot store values.
- Attempting to assign or retrieve values from a nil map results in a runtime error.
- Always initialize a map before using it using `make` or a map literal.

---
 #### Retrieving Values and Testing Existence

```go
// Retrieve a value from a map
quantity := myMap["apple"]

// Test if a key exists
if _, ok := myMap["banana"]; ok {
    fmt.Println("The key 'banana' exists in the map.")
} else {
    fmt.Println("The key 'banana' does not exist in the map.")
}
```

- Retrieve a value from a map by using the key as an index.
- Use the comma-ok idiom to test if a key exists in the map.
- The value `ok` is `true` if the key exists, otherwise `false`.

---
 #### Retrieving Values and Testing the Value for Existence

```go
// Retrieve a value and check existence
quantity, exists := myMap["apple"]
if exists {
    fmt.Println("The quantity of 'apple' is", quantity)
} else {
    fmt.Println("'apple' does not exist in the map")
}
```

- Use two variables to retrieve a value and check its existence.
- `exists` will be `true` if the key exists, otherwise `false`.

---
 #### Iterating over a Map using for Range

```go
// Iterate over the map using for range
for key, value := range myMap {
    fmt.Println(key, ":", value)
}
```

- Use a for range loop to iterate over a map.
- Each iteration provides a key-value pair which can be accessed using the variables in the loop declaration.

---
 #### Removing an Item from a Map

```go
// Remove an item from the map
delete(myMap, "apple")
```

- Use the `delete` function to remove a key-value pair from the map.
- Provide the map and the key to be deleted as arguments.

---

Passing Maps to functions
- Maps are reference types in Go, so when you pass a map to a function, you're actually passing a reference to the original map.
- Modifying the map within the function will also modify the original map outside the function.

```go{6,7|1-5|8}
func addToMap(m map[int]string) {
	m[1] = "One"
	m[2] = "Two"
	m[3] = "Three"
}
myMap := make(map[int]string)
addToMap(myMap)
fmt.Println("Map after adding values:", myMap)
```
```txt
Map after adding values: map[1:One 2:Two 3:Three]
```
{{% /section %}}