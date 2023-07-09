+++
+++

{{% section %}}
{{< slide id="methodSet" >}}

#### Method Sets
<!-- TODO: Needs more explanation -->
- Explain the concept of method sets.
- Method set of a type determines the interface it implements.
- Discuss value receiver vs. pointer receiver and their impact on method sets.

---
#### Method Sets Example
```go
type MyInt int

func (m MyInt) Print() {
    fmt.Println(m)
}

func (m *MyInt) Increment() {
    *m++
}

func main() {
    var i MyInt = 5
    i.Print()        // Output: 5
    var p *MyInt = &i
    p.Increment()
    p.Print()        // Output: 6
}
```


{{% /section %}}
