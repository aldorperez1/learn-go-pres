+++
+++

{{< slide id="functions-in-go" >}}
# Functions in Go

---
##### Intro
- Objectives: Understand the basics of functions in Go and learn best practices
- Topics covered: Functions, Multiple Return Values, Named Return Values, Variadic Functions, Anonymous Functions & Closures, Recursion, First-class Functions, Higher Order Functions

---

# Functions Recap

Syntax

```go
func functionName(parameters) returnType { ... }
```
Example
```go
func add(a, b int) int { 
    return a + b 
}
```

---
## Multiple Return Values

- Go supports returning multiple values from a function

```go{1,6}
func calculate(a, b int) (int, int) {
	return a + b, a - b
}
func main() {
	a, b := 1, 2
	foo, bar := calculate(a, b)
	fmt.Printf("foo: %d, bar: %d", foo, bar) 
    // OUTPUT: foo: 3, bar: -1
}
```

---
#### Named Return Values
- Go allows naming return values in function signatures
- Named return values are initialized with zero values by default
- Benefits of using named return values: improves code readability

```go{|1,4}
func calculateNamed(a, b int) (sum int, diff int) {
	sum = a + b
	diff = a - b
	return
}
func main() {
	sumResultNamed, diffResultNamed := calculateNamed(5, 3)
	fmt.Println("Sum (named):", sumResultNamed)
	fmt.Println("Difference (named):", diffResultNamed)
}
```

---
#### Variadic functions
- Variadic functions accept a variable number of arguments

Syntax:

```go
func functionName(parameters ...type) { ... }
```
Example
```go
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
---
#### Recursion
- Recursion is the process of a function calling itself
- Base case: condition that stops the recursive calls

```go
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
