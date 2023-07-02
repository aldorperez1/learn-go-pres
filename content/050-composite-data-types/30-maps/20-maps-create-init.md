+++
+++

{{% section %}}

# Creating and Initializing Maps in Go

---
## Declaring a Map Using Make
Syntax

```go
mapName := make(map[keyType]valueType, initialCapacity)
```
Example

```go
studentScores := make(map[string]int, 100)
```
---
## Declaring an Empty Map Using a Map Literal
Syntax

```go
mapName := map[keyType]valueType{}
```

Example

```go
employeeDetails := map[string]string{}
```
---
## Declaring a Map That Stores Slices of Strings
Syntax

```go
mapName := map[keyType][]valueType{}
```

Example

```go
attendeesByEvent := map[string][]string{}
```

{{% /section %}}