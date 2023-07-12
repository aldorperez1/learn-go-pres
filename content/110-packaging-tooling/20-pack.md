+++
+++

{{% section %}}

{{< slide id="packages" >}}
# Packages

- Introduction to the concept of packages in Go
- Importance of organizing and structuring code

---
# What are Packages?

- Packages as building blocks of Go programs
- Organize code into reusable and modular units
- Provide encapsulation and logical grouping of code

---
# How are Packages Used?

- Importing packages to access their functionality
- Syntax: `import "package/path"` or `import alias "package/path"`
- Accessing package members using the dot notation: `package.Member`

---
# Package Naming Conventions

- Importance of following naming conventions
- Short, concise, lowercase names with letters and numbers
- Relevant names reflecting the purpose or functionality
- Lowercase for packages not intended for external use

---
# Package main

- Introduction to the special `main` package
- Entry point for executable programs
- Must contain the `func main()`

---
# Package Visibility

- Understanding visibility within a package
- Capitalized identifiers: exported, accessible by other packages
- Lowercase identifiers: unexported, accessible within the same package

---
# Recap

- Packages organize and structure code in Go
- Importing packages to access their functionality
- Package naming conventions ensure consistency and readability
- The `main` package as the entry point for executables
- Package visibility determines accessibility of identifiers
{{% /section %}}