+++
+++

{{% section %}}

{{< slide id="multiIface" >}}

#### Implementing Multiple Interfaces
- Go allows types to implement multiple interfaces
- Multiple interfaces can help:
  - Interface Segregation
  - Clearer Contracts
  - Dependency Injection and Loose Coupling
  - Polymorphism and Code Reusability
  - Adapting to External Interfaces

{{% note %}}

Having multiple interfaces in Go allows for greater flexibility and modularity in designing and implementing code. 

Here are a just few reasons why you might want to use multiple interfaces:


**Interface Segregation**

Instead of having a single large interface, it's often better to define smaller, more focused interfaces that capture specific behaviors or roles.
This promotes code reusability and makes it easier to reason about and test individual components.

**Clearer Contracts**

Each interface represents a specific set of methods or behaviors, making it easier to understand and communicate the intended usage and requirements of different parts of the codebase.


**Dependency Injection and Loose Coupling**

By depending on interfaces rather than concrete types, you can easily swap out implementations at runtime or during testing.
This promotes flexibility, modularity, and testability in your code.

**Polymorphism and Code Reusability**

Multiple interfaces enable polymorphism, allowing different types to be used interchangeably as long as they satisfy the required interfaces.
This promotes code reusability and modularity by providing a common interface that various types can adhere to.
It allows you to write generic algorithms and functions that can operate on any type that satisfies a specific interface.

**Adapting to External Interfaces**

When working with external libraries or APIs that define their own interfaces, having multiple interfaces can help you adapt your code to fit those interfaces seamlessly.
By defining interfaces in your code that match the external interfaces, you can write adapters or wrappers that bridge the gap between your code and the external code.

{{% /note %}}

---
#### Example: Multiple Interface

```go
type Writer interface {
    Write(data []byte) (int, error)
}

type Closer interface {
    Close() error
}

type FileWriter struct {
    // Fields and implementations
}

func (fw FileWriter) Write(data []byte) (int, error) {
    // Write implementation
}

func (fw FileWriter) Close() error {
    // Close implementation
}
```
---
#### Example: Multiple Interfaces cont.

```go
func main() {
    var w Writer
    var c Closer

    file := FileWriter{}
    w = file
    c = file

    // File can be treated as both Writer and Closer
}
```

{{% /section %}}