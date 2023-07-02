+++
+++

{{% section %}}

# Iterating Over Slices in Go

---

## Iterating Over a Slice using `for range`
- Syntax: `for index, value := range slice`
- `range` provides a copy of each element
- Benefits: simplicity, avoidance of off-by-one errors

---
Example 1: Iterating Over a Slice using `for range`
```go
intSlice := []int{10, 20, 30, 40, 50}
for _, value := range intSlice {
    fmt.Println(value)
}
```
Output:
```
10
20
30
40
50
```

---
## Using the Blank Identifier to Ignore Index Value
- Syntax: `for _, value := range slice`
- `_` signals intentional unused index value

---
Example 2: Using the Blank Identifier to Ignore Index Value
```go
strSlice := []string{"apple", "banana", "cherry", "date"}
for index, value := range strSlice {
    fmt.Printf("Index: %d, Value: %s\n", index, value)
}
```
Output:
```
Index: 0, Value: apple
Index: 1, Value: banana
Index: 2, Value: cherry
Index: 3, Value: date
```

---
## Iterating Over a Slice using a Traditional `for` Loop
- Syntax: `for i := 0; i < len(slice); i++`
- Provides fine-grained control over the iteration

---
Example 3: Iterating Over a Slice using a Traditional `for` Loop
```go
floatSlice := []float64{3.14, 1.618, 2.718, 0.577}
sum := 0.0
for i := 0; i < len(floatSlice); i++ {
    sum += floatSlice[i]
}
fmt.Println("Sum:", sum)
```
Output:
```
Sum: 7.027
```

{{% /section %}}