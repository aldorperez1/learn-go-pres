+++
+++

{{% section %}}

{{< slide id="modules" >}}
# Go Modules
- Go Modules are a dependency management system in Go.
- They simplify dependency management, versioning, and reproducibility.
- Benefits:
  - Better compatibility
  - Simplified collaboration
  - Improved project organization
  - Enhanced dependency version control

---
# Why Do We Need Go Modules?

- Challenges of manual dependency management
- Benefits of Go Modules:
  - Versioning and reproducibility
  - Simplified dependency management
  - Easy sharing and collaboration
  - Improved compatibility

---
# Creating Go Modules

- Project Structure:
  - Create projects outside of `$GO/src`
  - Recommended project structure
- Initializing a Go Module:
  - `go mod init`
  - Creates a `go.mod` file to manage dependencies

---
# Managing Dependencies

- Adding Dependencies:
  - `go get`
  - Fetches and adds dependencies to `go.mod`
- Removing Dependencies:
  - `go mod tidy`
  - Removes unused dependencies and updates `go.mod` and `go.sum` files

---
# Go Module Commands

- `go mod init`: Initialize a new Go Module
- `go get`: Add a dependency to a Go Module
- `go mod tidy`: Remove unused dependencies and update module files
- `go mod download`: Download dependencies specified in `go.mod`
- `go list -m all`: List all dependencies of a Go Module
{{% /section %}}