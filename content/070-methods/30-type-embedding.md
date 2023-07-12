+++
+++

{{% section %}}
{{< slide id="typeEmbed" >}}

#### Type Embedding
- A struct can embed fields from other structs.

---
#### Type Embedding Example
```go
type Person struct {
    name string
    age  int
}

type Employee struct {
    Person
    role string
}

func main() {
    emp := Employee{
        Person: Person{
            name: "John",
            age:  30,
        },
        role: "Developer",
    }
    fmt.Println(emp.name) // Output: John
    fmt.Println(emp.age)  // Output: 30
    fmt.Println(emp.role) // Output: Developer
}
```

[Back to Home](..)
{{% /section %}}
