+++
+++

{{% section %}}

## Golden Files in Go 👑

---

#### What are golden files and why do we need them?

- Hardcoding the expected values in an assertion is a straightforward approach in testing.
- However, things can get tricky when we are testing a unit whose output is cumbersome to hardcode e.g a large json structure.
- We could just have the expected outcome stored in a file
- In Go, we call such files golden files.
- Golden files contain the expected output of a test.
- When tests run, they read the contents of the golden file and compare it to the output of the unit under test.


---
#### What are golden files and why do we need them? (cont.)

- Golden files are particularly useful for testing outputs that are large, complex, or difficult to define programmatically.
- They serve as a form of regression testing, allowing you to ensure that the output remains consistent over time.

---
#### Working with Golden Files

1. Create a golden file:
   - Run your test with the `WRITE_GOLDEN=true` environment variable.
   - The test generates the actual output and writes it to a file.
   - Review the generated file and verify its correctness.

2. Compare against the golden file:
   - Run your test normally.
   - The test compares the actual output against the contents of the golden file.
   - If the outputs match, the test passes.
   - If they differ, the test fails, indicating a regression.

---
#### Considerations for Golden Files

- Keep golden files under version control.
- Update golden files intentionally when the changes in output are expected.
- Document any changes made to golden files to maintain transparency.


{{% /section %}}