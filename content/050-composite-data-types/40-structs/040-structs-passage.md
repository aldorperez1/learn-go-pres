+++
+++

{{% section %}}
#  Passing Structs to Functions

---

#### Passing by value

- Passing without `&` passes a copy of the struct to the function
- Any changes to it will be made to copy of struct and not the original

```go
type Point struct {
	x int
	y int
}

func modifyValue(point Point) {
	point.x += 10
}
p := Point{0, 0}
fmt.Println(p) // prints (0, 0)
modifyValue(p)
fmt.Println(p) // Still prints (0, 0)
```
---

#### Passing by Reference
- Use `&` to pass a reference of the struct to the function
- The function has its own copy of a pointer
- Any changes made to the struct will take effect to the original struct

```go
func modifyPointer(point *Point) {
	point.x = 5
	point.y = 5
}
p := Point{0, 0}
fmt.Println(p) // prints (0, 0)

modifyPointer(&p)
fmt.Println(p) // prints (5, 5)
```
---

#### Trying to modify reference inside function
- Since its only a copy of a reference, it only changes the reference inside the function
- Original reference is intact

```go
func modifyReference(point *Point) {
	point = &Point{6, 6}
}
p := Point{0, 0}
fmt.Println(p) // prints (0, 0)

modifyReference(&p)
fmt.Println(p) // prints (0, 0)

```

{{% note %}}
What happens when you try to modify the reference inside the function?
{{% /note %}}

{{% /section %}}