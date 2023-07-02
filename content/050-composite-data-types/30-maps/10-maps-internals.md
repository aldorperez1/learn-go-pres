+++
+++

{{% section %}}

## Introduction to Maps & Internals

---

## What are maps?
- Maps are unordered collections of key-value pairs.
- They provide efficient lookup, insertion, and deletion operations.
- Syntax: `map[keyType]valueType`.

---
## Map Implementation Details
a. Hash Function
- Converts keys into hash codes.
- Importance of a good hash function.

---
## Map Implementation Details
b. Buckets and Buckets Array
- Buckets store key-value pairs.
- Buckets array organizes elements.

---
## Map Implementation Details
c. Collision Handling
- Collisions occur when hash codes clash.
- Separate chaining and open addressing.

---
## Map Implementation Details
d. Growth and Rehashing
- Dynamically expands capacity.
- Factors triggering growth.

{{% /section %}}