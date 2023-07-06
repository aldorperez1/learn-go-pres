+++
+++

{{% section %}}

# Goroutines
aka lightweight🪶 threads ⚡️

---

### What are Goroutines?
- Lightweight concurrent functions or threads of execution in Go
- Allow multiple functions to run concurrently within a single program
---

### Key Features of Goroutines
- Lightweight and small memory footprint
- Enable concurrent execution without explicit thread management
- Communication through channels

---

#### How do goroutines differ from threads

- Lightweight, efficient and cheaper than kernel threads
- Smaller memory footprint
- Faster creation, destruction & context-switching
- Managed by runtime scheduler instead of OS scheduler
  - Multiplexes goroutines to threads rather than processors
- Multiplex onto a smaller number of OS threads (typically 1 thread per CPU to maximize parallelism)

---

### Using Goroutines
- Creating Goroutines: 
- `go functionName(arguments)`

```go
  func sayHello() {
      fmt.Println("Hello")
  }

  func main() {
      go sayHello() // Create a goroutine to execute sayHello()
      time.Sleep(time.Second) // Wait for goroutine to finish before program exits
  }
```
---

Can also pass in anonymous functions

```go
func main() {
	go func() {
		for i := 0; i < 5; i++ {
			fmt.Println("Goroutine:", i)
			time.Sleep(time.Second)
		}
	}()

	// Waiting for goroutine to finish
	time.Sleep(3 * time.Second)
	fmt.Println("Main goroutine exiting")
}
```

---

# Exercise Time 🏋️‍♀️

{{% /section %}}