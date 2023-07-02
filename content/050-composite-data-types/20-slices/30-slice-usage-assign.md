+++
+++

{{% section %}}

### Slice: Assigning and Slicing

---
## Declaring an array using an array literal

```go
// Declaring an array using an array literal
arr := [5]int{1, 2, 3, 4, 5}
```
- Arrays have a fixed length in Go.
- Array literals allow us to declare an array with initial values.

---
## Taking the slice of a slice

- Slicing creates a new slice from an existing slice or array.
- The resulting slice includes elements from the specified range.

```go
// Taking the slice of a slice
slice := arr[2:4]
```

---
## How length and capacity are calculated

```go
// How length and capacity are calculated
length := len(slice)
capacity := cap(slice)
```
- `len(slice)` returns the number of elements in the slice.
- `cap(slice)` returns the maximum number of elements the slice can hold.

---
## Calculating the new length and capacity

- Taking a slice of a slice can change the length and capacity.
- The new length is determined by the range of elements in the new slice.
- The new capacity is calculated based on the original slice's capacity.
  
```go
// Calculating the new length and capacity
newSlice := slice[1:3]
newLength := len(newSlice)
newCapacity := cap(newSlice)
```

---
## Potential consequence of making changes to a slice

- Slices in Go are reference types.
- Modifying a slice can affect other slices sharing the same underlying array.

```go
slice[0] = 10
```

---
## Index out of range

- Accessing an index that is out of range will result in a runtime error.
- Go will panic and display an "index out of range" error message.

```go
element := slice[10]
```


{{% /section %}}