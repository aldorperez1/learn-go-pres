+++
+++

{{% section %}}

{{< slide id="embedIface" >}}

#### Interface Embedding
- Interface embedding is a way to compose/embed interfaces.

---
#### Example
```go
type Shape interface {
    Area() float64
}

type Perimeter interface {
    Perimeter() float64
}

type Geometry interface {
    Shape
    Perimeter
}

type Rectangle struct {
    width, height float64
}
```
---
#### Example (continued)

```go
func (r Rectangle) Area() float64 {
    return r.width * r.height
}

func (r Rectangle) Perimeter() float64 {
    return 2 * (r.width + r.height)
}

func main() {
    rect := Rectangle{width: 10, height: 5}
    var g Geometry = rect
    fmt.Println(g.Area())       // Output: 50
    fmt.Println(g.Perimeter())  // Output: 30
}
```

{{% /section %}}