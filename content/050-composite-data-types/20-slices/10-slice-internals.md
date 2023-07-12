+++
+++

{{% section %}}

## Slice Internals
---
## Slice Header

- A slice in Go consists of a header structure that holds metadata about the slice.
- A slice header has three fields:
  - Pointer: Memory address of the underlying array.
  - Length: Number of elements currently in the slice.
  - Capacity: Maximum number of elements the slice can hold without reallocation.

---
## Length and Capacity
- A slice has length and capacity:
  - Length: Number of elements present in the slice.
  - Capacity: Total number of elements the current slice can accommodate.
- Length and capacity are usually the same when a slice is created.

---
## Underlying Array
- A slice does not store its own data directly but references an underlying array.
- The pointer field in the slice header points to the memory address of the first element in the array.

{{% /section %}}