+++
+++


#### Introduction to Methods
- Methods are functions associated with a type
- Define behavior specific to a type
- Declared and defined within the scope of a type

---
#### Declaration of a Method with a Value Receiver
- Operates on a copy of the value
- Does not modify the original value

```go
func (v Type) methodName() {
    // Method implementation
}
```
---
#### Example: Method with a Value Receiver
```go
type Rectangle struct {
    width, height float64
}

func (r Rectangle) Area() float64 {
    return r.width * r.height
}
```

---
#### Declaration of a Method with a Pointer Receiver
- Operates directly on the original value
- Can modify the value
- Syntax:
```go
func (p *Type) methodName() {
// Method implementation
}
```

---
#### Example: Method with a Pointer Receiver

```go
type Rectangle struct {
    width, height float64
}

func (r *Rectangle) Scale(factor float64) {
    r.width *= factor
    r.height *= factor
}
```

---
#### Calling a Method from a Variable
- Use dot notation on a variable of the associated type
- Method invoked based on the receiver type (value or pointer)

```go
rect := Rectangle{width: 10, height: 5}
area := rect.Area()
rect.Scale(2)
```

---

#### Choosing Between Pointer vs Value Receiver
- Value Receiver:
  - When the method does not modify the value
- Pointer Receiver:
  - When the method needs to modify the value or avoid unnecessary copying
- Consider semantics and behavior of the type

---

#### Underlying Mechanism of Method Association
- Automatic conversion between values and pointers
- Go determines relationship between methods and types
- Call methods conveniently without explicitly dealing with values or pointers

---
#### Visibility of Methods in Go


- Exported Types and Methods
  - Start with an uppercase letter
  - Accessible and usable by other packages
  - Part of the public API of a package

- Unexported Types and Methods
  - Start with a lowercase letter
  - Only accessible within the same package
  - Not visible to other packages

---
#### Example: Visibility of Methods

```go
type MyStruct struct {
	name string // Unexported field
}
func (m MyStruct) ExportedMethod() {
	fmt.Println("This is an exported method.")
}
func (m MyStruct) unexportedMethod() {
	fmt.Println("This is an unexported method.")
}
func main() {
	myVar := MyStruct{name: "John Doe"}
	myVar.ExportedMethod() // Accessing an exported method
	// myVar.unexportedMethod() // Trying to access an unexported method 
    // will result in a compile-time error
}
```
