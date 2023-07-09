+++
+++

{{% section %}}
{{< slide id="var" >}}

# Variables 

---
#### Declaration
- In Go, a variable declaration creates a variable of a particular type, assigns a name to it, and can set an initial value.

```go
var name type = expression
```
---
#### Zero Value Initialization
- Uninitialized variables do not exist in Go. They are always initialized with a well-defined value based on their type.
- Zero values for common types: 0 for numbers, false for booleans, "" for strings, and nil for reference types.

```go
var s string
fmt.Println(s) // ""
```
---
#### Initializing Multiple Variables
- Multiple variables can be declared and initialized in a single declaration.
- Omitting the type allows declaration of variables of different types.

```go{3-4}
var s string
fmt.Println(s) // ""
var i, j, k int //int int int
var b, f, s = true, 2.3, "four" // bool, float64, string
```

---
#### Initialization with Function Return Values
- Variables can be initialized by calling a function that returns multiple values.

```go{5}
var s string
fmt.Println(s) // ""
var i, j, k int //int int int
var b, f, s = true, 2.3, "four" // bool, float64, string
var f, err = os.Open(name)
```

---
#### Short Variable Declarations
- Go provides a concise syntax for declaring and assigning variables using the short variable declaration (`:=`) operator.
- It allows you to declare and initialize variables without explicitly specifying the type.

Syntax:
```go
variableName := expression
```

Example:
```go
name := "John"
age := 30
isActive := true
```

---
#### Benefits of Short Variable Declarations
- Concise: Reduces the need for repetitive type specification.
- Readability: Makes code more compact and easier to understand.
- Scope: Variables declared using short variable declarations are limited to the innermost block where they are declared.

---
#### Limitations of Short Variable Declarations
- Short variable declarations can only be used for declaring and assigning new variables within the same block.
- They cannot be used for reassigning or updating the value of an existing variable.


---
#### Scope of Variables
- The scope of a variable determines where it is accessible within the program.
- Variables can have package-level scope or local scope within functions.
- Package-level variables are initialized before `main()`, while local variables are initialized during function execution.


{{% /section %}}