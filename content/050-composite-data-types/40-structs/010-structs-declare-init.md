
## Struct Types
- Structs are composite data types that group together zero or more values with different types.
- Declaration syntax:

```go
type StructName struct {
    field1 fieldType1
    field2 fieldType2
    // ...
}
```

---
## Struct Variables
- Declare a variable of struct type and set it to its zero value:

```go
type Person struct {
    name string
    age  int
}

var p Person // p is set to the zero value of the Person struct type
```

---
## Struct Literals
- Declare a variable of struct type using a struct literal:

```go
p := Person{name: "John", age: 30} // p is assigned a struct literal with specific field values
```

---
## Creating Struct Values
- Create a struct value directly using a struct literal:

```go
john := Person{name: "John", age: 30} // Creating a Person struct value without assigning it to a variable
```

---
## Struct Value without Field Names
- Creating a struct value without declaring field names (using the order of fields):

```go
p := Person{"John", 30} // Creating a Person struct value without declaring field names
```

---
## Fields Based on Other Struct Types
- Declare fields based on other struct types to compose complex data structures:

```go
type Address struct {
    street  string
    city    string
    country string
}

type Person struct {
    name    string
    age     int
    address Address // Using the Address struct type as a field in the Person struct type
}
```

---
## Pointers to Structs
- Use pointers to structs for indirect access and modification of underlying struct values:
```go
p := &Person{name: "John", age: 30} // p is a pointer to a Person struct
```
