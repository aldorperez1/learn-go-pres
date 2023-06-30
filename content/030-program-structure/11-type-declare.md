+++
+++

{{% section %}}

# Type Declaration in Go

  - Type declaration in Go allows you to create custom, named types that are aliases or new representations of existing types.
  - It provides a way to define a new type name with the same underlying type, creating a distinct type identity.
---
## Reasons for Using Type Declaration
- Code Clarity and Readability
- Type Safety and Enforcement
- Abstraction and Encapsulation
- API Design and Documentation

{{% note %}}
- can improve code readability by giving meaningful names to types and making the code more self-explanatory.
- enable you to create more explicit and type-safe interfaces, reducing the chances of errors and improving code reliability.
- allow you to abstract away implementation details and encapsulate functionality within custom types, promoting code modularity and maintainability.
- help in designing clean and well-documented APIs by providing clear and descriptive type names that convey the purpose and usage of the underlying data.
{{% /note %}}

---
#### Example: Type Declaration


```go
type Celsius float64
type Fahrenheit float64

func main() {
    var temperature Celsius = 25.5
    fmt.Println("Temperature:", temperature, "°C")
}
```


{{% note %}}
- In the example, we declare two custom types, `Celsius` and `Fahrenheit`, as aliases of the `float64` type.
- The `Celsius` and `Fahrenheit` types provide distinct type identities, allowing us to differentiate between temperature values in different scales.
- We then declare a variable `temperature` of type `Celsius` and assign it a value of `25.5`.
{{% /note %}}


{{% /section %}}