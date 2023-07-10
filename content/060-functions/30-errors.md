+++
+++

{{% section %}}
{{< slide id="errors" >}}
# Errors in Go

---
## Introduction to Error Handling
- Error handling is essential for robust software development.
- In Go, error handling is explicit and encourages the use of return values to indicate errors.
- Go provides built-in mechanisms for error handling to ensure reliable and predictable behavior.

---
## Errors in Go
- Errors in Go are represented by the `error` interface type.
- The `error` interface has a single method: `Error() string`, which returns the error message.
- Both recoverable and unrecoverable errors can be represented using the `error` type.

---
#### Overview

- Many functions throw errors as part of their return values
- Usually, return values are on the right
- You must then inspect the `error` variable once you get it

```go
file, err := os.Open("file.txt")
if err != nil {
    fmt.Printf("Couldn't open file")
}
```
---

## Creating Custom Errors
- When you need to create an error instead of being passed an error use either `errors.New(string)` or `fmt.Errorf(string)` to create your error.
- Then return your error to the caller


```go
import errors
...
// Using errors.New
import "errors"
err := errors.New("error message")

// Using fmt.Errorf
import "fmt"
err := fmt.Errorf("error: %s", otherErr)
```

---
## Creating Custom Errors (continued)
```go
func divide(a, b int) (int, error) {
	if b == 0 {
		return 0, errors.New("division by zero")
	}
	return a / b, nil
}
func main() {
	numerator := 10
	denominator := 0
	result, err := divide(numerator, denominator)
	if err != nil {
		fmt.Printf("Error: %s\n", err.Error())
		return
	}
	fmt.Printf("Result: %d\n", result)
}
```
---
## Creating a Custom Error - Reusable
- To define a common error, you must implement the `Error` interface

```go
type error interface {
    Error() string
}
```
Example
```go
type NoNameProvided struct{}
func (e NoNameProvided) Error() string {
	return "No Name Provided"
}
```
---
## Creating a Custom Error - Reusable (continued)
Example (continued)
```go
func sayHello(s string) (string, error) {
	if s == "" {
		return "", &NoNameProvided{}
	}
	return fmt.Sprintf("Hello %s", s), nil
}
...
res, err := sayHello("")
if err != nil {
    fmt.Printf("Error: %s\n", err.Error())
} else {
    fmt.Printf(res)
}
```



{{% /section %}}