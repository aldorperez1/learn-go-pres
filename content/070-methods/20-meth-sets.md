+++
+++

{{% section %}}
{{< slide id="methodSet" >}}

#### Method Sets
- Method set of a type determines the interface it implements.
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
