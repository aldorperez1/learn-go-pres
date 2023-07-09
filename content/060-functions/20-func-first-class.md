+++
+++

{{% section %}}

{{< slide id="firstClassFunctions" >}}
# First Class Functions

---
#### First-Class Functions in Go
- In Go, functions are first-class citizens
- Functions can be assigned to variables, passed as arguments, and returned as values
- Enable flexibility, modularity, reusability, and improved concurrency in your code.
- Equips you for: functions as values, callbacks, function composition,higher-order functions, anonymous functions, concurrent programming, and dependency injection


{{% note %}}

Overall, the use of first-class functions in Go empowers you to write more flexible, modular, and reusable code. It enables you to create higher-order functions, compose functions, implement callbacks, and leverage concurrency effectively.

{{% /note %}}

---

#### Anonymous functions

- Anonymous functions are functions without names
- They can be assigned to variables or invoked directly
- Example: 

```go
add := func(a, b int) int {
    return a + b
}
result := add(2, 3)
fmt.Println("Result of anonymous function:", result)
```
---
#### Closures

- Closures: Anonymous functions that access variables from their surrounding scope

```go
func main() {
	x := 5
	increment := func() int {
		x++
		return x
	}
	fmt.Println("Closure result:", increment()) // Closure result: 6
	fmt.Println("Closure result:", increment()) // Closure result: 7
}
```

---
#### Higher-Order function

- Higher-order functions take one or more functions as arguments or return a function

```go
func multiply(a, b int) int {
	return a * b
}
func sum(a, b int) int {
	return a + b
}
func applyOperation(op func(int, int) int, a int, b int) int {
	return op(a, b)
}
func main() {
	resultMult := applyOperation(multiply, 4, 5)
	resultSum := applyOperation(sum, 4, 5)
	fmt.Println("Result of applyOperation multiply:", resultMult)
	fmt.Println("Result of applyOperation sum:", resultSum)
}
```

{{% /section %}}