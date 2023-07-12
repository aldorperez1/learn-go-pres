+++
+++

{{% section %}}

# Writing and Running Unit Tests ⛔️✅
---
#### Introduction to Testing
- Importance of testing in software development
  - Ensures code correctness, reliability, and maintainability
  - Helps catch bugs early in the development process
- Benefits of automated testing
  - Saves time and effort by automating the testing process
  - Provides a safety net for code refactoring and changes
- Introduction to unit testing and its role in Go development
  - Focuses on testing individual units of code (functions, methods, packages)
  - Ensures the units work correctly in isolation

---
#### Writing and Running Unit Tests
- Creating a Test File
  - Test files should have a "_test.go" suffix (e.g., "mycode_test.go")
  - Place test files in the same package as the code being tested
  - Use package and import statements to access the code being tested

```go
package mypackage_test

import (
    "testing"
    "mypackage"
)
```
---
#### Writing Test Functions
- Test functions should have a "Test" prefix (e.g., "TestMyFunction")
- Test functions should accept a *testing.T parameter for reporting test results
- Write individual test cases within test functions using assertions

---
```go
func TestMyFunction(t *testing.T) {
    // Test case 1
    // Assertion using t.Errorf
    if result := mypackage.MyFunction(2); result != 4 {
        t.Errorf("Expected 4, but got %d", result)
    }

    // Test case 2
    // Assertion using t.FailNow
    if result := mypackage.MyFunction(5); result != 10 {
        t.FailNow()
    }
}
```
---
#### Running Tests
- Use the "go test" command to run tests in the terminal
- Running all tests in a package: `go test`
- Running specific tests or test functions: `go test -run TestFunctionName`
- View test output and results, including pass/fail information

---
#### Common Test Functions and Techniques
- Setup and teardown functions: used for test setup and cleanup
- Use `t.Fatal` and `t.Error` for reporting test failures
- Skip tests using `t.Skip` for conditions not met
- Test for expected errors or specific behavior in code

---
# Exercise 🏋️‍♀️

```shell
cd 120-testing/01-write-tests
```

{{% /section %}}