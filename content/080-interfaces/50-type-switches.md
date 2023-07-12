+++
+++

{{% section %}}

{{< slide id="typeSwitch" >}}

#### Type Switches
- A `switch`-like construct that permits multiple type assertions in series

Example:
```go
switch data.(type) {
    case string:
      // string type
    case int:
      // int type
    case float64:
      // float64 type
    default:
      // unknown or default type
   }
```

[Back to Home](..)
{{% /section %}}

