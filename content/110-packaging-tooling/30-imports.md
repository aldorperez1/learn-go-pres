+++
+++

{{% section %}}

{{< slide id="imports" >}}
# Imports
- Introduction to the concept of imports in Go
- Importance of imports in accessing external packages and dependencies

---
# How do Imports Work in Go?

- Imports allow accessing functionality from external packages
- Syntax: `import "package/path"` or `import alias "package/path"`
- Imported packages are referenced using the dot notation: `package.Member`

---
# How Does Go Look for Dependencies?

- Go uses the import path to find source code of imported packages
- Compiler searches in GOPATH (default: $HOME/go)
- Go tooling supports fetching dependencies from version control systems

---
# Remote Imports

- Sharing code through Distributed Version Control Systems (DVCS) like GitHub
- Go tooling supports fetching dependencies from version control sites
- Import path indicates the location of the source code

---
# Compiler's Search for Remote Imports

- Building a program triggers the compiler to search for remote imports
- Compiler searches GOPATH for the package locally
- If not found, it prompts to download the dependency
- The package name indicates the source code location

---
# Adding Remote Imports to Your Project

- Steps to add remote imports:

1. Use import statement with the package path
2. Build the program
3. If dependencies are missing, use `go get` to download them

---
# Named Imports

- Importing a package with a custom alias
- Useful for avoiding naming conflicts or providing more descriptive names
- Syntax: `import alias "package/path"`

---
# Blank Identifier for Imports

- Importing a package solely for side effects
- Using the blank identifier `_`
- Syntax: `import _ "package/path"`

---
# Init Function

- Optional `init` function in packages
- Runs automatically during program initialization
- Used for package setup or initialization tasks

{{% /section %}}