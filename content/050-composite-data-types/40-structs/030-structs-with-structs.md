+++
+++

{{% section %}}

# Structs Containing Other Structs


---
#### Structs Containing Other Structs

- Structs can be composed of other structs

```go
type Address struct {
    Street  string
    City    string
    Country string
}

type Person struct {
    Name    string
    Age     int
    Address Address
}
```
---
#### Structs Containing Other Structs cont.
- Initialize the struct
- Access the internal components with dot notation
  
```go
func main() {
    // Creating a struct with nested structs
    person := Person{
        Name: "John",
        Age:  25,
        Address: Address{
            Street:  "123 Main St",
            City:    "New York",
            Country: "USA",
        },
    }

    // Accessing fields of nested structs
    fmt.Println("Name:", person.Name)
    fmt.Println("Age:", person.Age)
    fmt.Println("Street:", person.Address.Street)
    fmt.Println("City:", person.Address.City)
    fmt.Println("Country:", person.Address.Country)
}
```

{{% /section %}}