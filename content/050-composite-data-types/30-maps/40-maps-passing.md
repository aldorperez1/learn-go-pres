+++
+++

{{% section %}}

# Passing Maps to functions

---
Passing Maps to functions
- Maps are reference types in Go, so when you pass a map to a function, you're actually passing a reference to the original map.
- Modifying the map within the function will also modify the original map outside the function.

```go{6,7|1-5|8}
func addToMap(m map[int]string) {
	m[1] = "One"
	m[2] = "Two"
	m[3] = "Three"
}
myMap := make(map[int]string)
addToMap(myMap)
fmt.Println("Map after adding values:", myMap)
```
```txt
Map after adding values: map[1:One 2:Two 3:Three]
```

{{% /section %}}