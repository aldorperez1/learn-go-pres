+++
+++

{{% section %}}

{{< slide id="typeAssert" >}}

#### Type Assertions
- Provide access to the underlying typed concrete value of an interface-typed variable
- In the example below, `value` must be an interface-typed variable

```go
t, ok := value.(typeName)
```

{{% /section %}}