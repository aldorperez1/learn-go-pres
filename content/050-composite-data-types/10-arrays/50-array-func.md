+++
+++

{{% section %}}

# Passing Arrays Between Functions

---
#### By Value

```go
func modifyArrayByValue(array [5]int) {
	array[0] = 10
}

func main() {
	array := [5]int{1, 2, 3, 4, 5}
    fmt.Println("Original array:", array)
	modifyArrayByValue(array)
	fmt.Println("After modifyArrayByValue:", array)
}
```

```txt
Original array: [1 2 3 4 5]
After modifyArrayByValue: [1 2 3 4 5]
```

---
#### By Pointer

- To avoid making a copy, arrays can be passed by pointer.
- Changes made to the array in the function do affect the original array

```go{6}
func modifyArrayByPointer(arr *[3]int) {
    (*arr)[0] = 10
}

array := [3]int{1, 2, 3}
modifyArrayByPointer(&array)
fmt.Println("After modifyArrayByPointer:", array)
```

```txt
Original array: [1 2 3]
After modifyArrayByPointer: [10 2 3]
```

{{% /section %}}