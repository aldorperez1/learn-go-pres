+++
+++

{{% section %}}

# Writing Assertions using Stretchr/testify ⛔️✅

---
#### Writing Assertions using Stretchr/testify
- A popular testing library for Go with enhanced assertion capabilities
- Provides a set of assertion functions for cleaner and more readable tests
- Offers additional functionalities for mocking, stubbing, and more
- Install the package using the "go get" command

```shell
go get github.com/stretchr/testify
```
---
### Writing Assertions
- Use the assertion functions provided by `Stretch/testify`
- Assert equality with `assert.Equal`
- Check for true/false conditions with `assert.True/assert.False`
- Assert errors with `assert.Error/assert.NoError`
- Additional assertion functions available for different scenarios

---

```go
import (
    "testing"
    "github.com/stretchr/testify/assert"
)
func TestMyFunction(t *testing.T) {
    // Assertion using assert.Equal
    assert.Equal(t, 4, mypackage.MyFunction(2))
    // Assertion using assert.True
    assert.True(t, someCondition)
    // Assertion using assert.Error
    assert.Error(t, err)
}
```
---
#### Advanced Assertion Techniques
- Check for expected panics with `assert.Panics`
- Assert the length and contents of slices and arrays
- Compare complex structures using `assert.ObjectsAreEqual`
- Customize error messages in assertions for better diagnostics

---
# Exercise 🏋️‍♀️

```shell
cd 120-testing/01-write-tests
```
{{% /section %}}