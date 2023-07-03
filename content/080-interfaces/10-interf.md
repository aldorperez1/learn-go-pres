+++
+++

{{% section %}}
# Intro to interfaces

---

#### What are Interfaces?
- An interface is a collection of method signatures.
- In Go, interfaces define behavior, not structure.
- A type a type implicitly implements an interface if it contains all the methods defined in the interface.
- They enable code reuse and flexibility in Go programs.
- Different types can be treated interchangeably if they implement the same set of methods.

---
#### How do you implement an interface?
- A type a type **implicitly** implements an interface if it contains all the methods defined in the interface.
- No need to label it as `implements`

---
#### Example: Interfaces
  
```go
type Shape interface {
	Area() float64
}
type Rectangle struct {
    width, height float64
}
func (r Rectangle) Area() float64 {
    return r.width * r.height
}
func printArea(s Shape) {
    fmt.Printf("Area: %f\n", s.Area())
}
func main() {
	rect := Rectangle{width: 10, height: 5}
	printArea(rect)
}

```
---
#### Example: Interfaces implemented by many types

```go
type Circle struct {
	radius float64
}
func (c Circle) Area() float64 { // Implements interface
	return math.Pi * math.Pow(c.radius, 2)
}
...
rect := Rectangle{width: 10, height: 5}
circ := Circle{3}
printArea(rect) // Output:Area: 50.000000
printArea(circ) // Output: Area: 28.274334
```
---
#### Polymorphism in Go
- Interfaces allow for polymorphic behavior

```go
type Animal interface {
    Speak() string
}

type Dog struct{}

func (d Dog) Speak() string {
    return "Woof!"
}

type Cat struct{}

func (c Cat) Speak() string {
    return "Meow!"
}

func main() {
    animals := []Animal{Dog{}, Cat{}}
    for _, animal := range animals {
        fmt.Println(animal.Speak())
    }
}
```

{{% /section %}}