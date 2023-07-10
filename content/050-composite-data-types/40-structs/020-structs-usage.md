+++
+++

{{% section %}}

# Modifying structs

- Use `.` to access the structs fields and to assign new values

```go
type Person struct {
    Name    string
    Age     int
    Country string
}
person := Person{
    Name:    "John",
    Age:     25,
    Country: "USA",
}
person.Age = 30
person.Country = "Canada"
fmt.Println("Modified struct:", person)
```


{{% /section %}}