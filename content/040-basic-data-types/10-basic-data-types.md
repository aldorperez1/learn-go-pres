#### Basic Data Types in Go:
- Go provides several basic data types to represent different kinds of values.
- Understanding these data types is essential for working with variables and performing operations on them.

---
#### Integers:
- Integers represent whole numbers without decimal points.
- They can be signed (positive, negative, or zero) or unsigned (only positive or zero).
- Common integer types in Go include: `int`, `int8`, `int16`, `int32`, `int64`, `uint`, `uint8`, `uint16`, `uint32`, and `uint64`.

```go
var age int = 25
var size uint32 = 50
var atomsInUniverse uint64 = 123445343
```

---
#### Floating-Point Numbers:
- Floating-point numbers represent numbers with decimal points.
- They can be represented using float32 (single-precision) or float64 (double-precision) types.

```go
var pi float64 = 3.14159
```
---
#### Complex Numbers:
- Complex numbers represent values with both real and imaginary parts.
- They are represented using complex64 (float32 real and imaginary parts) or complex128 (float64 real and imaginary parts) types.

```go
var c complex128 = complex(3, 4)
```
---
#### Booleans:
- Booleans represent logical values: true or false.
- They are represented using the bool type in Go.

```go
var isGoFun bool = true
```
---
#### Strings:
- Strings represent a sequence of characters.
- They are represented using the string type in Go.
- Strings are immutable, meaning their values cannot be changed once created.

```go
var greeting string = "Hello, Go!"
```

---
#### Constants:
- Constants are fixed values that cannot be changed during program execution.
- They are declared using the const keyword and are assigned a value at the time of declaration.
- Constants provide named values for repeated use and enhance code readability.

```go
const gravity float64 = 9.8
```
---
#### Comparison Operators:
- Comparison operators are used to compare values and produce a boolean result (true or false).
- Common comparison operators in Go include == (equal to), != (not equal to), < (less than), > (greater than), <= (less than or equal to), and >= (greater than or equal to).

```go
x := 10
y := 5
isEqual := x == y
isGreaterThan := x > y
isNotEqual := x != y
```
