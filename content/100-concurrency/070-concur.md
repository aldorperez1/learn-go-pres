+++
+++

{{% section %}}


# 👆Select Statement and Timeouts ⏱️


---
#### Select Statement Overview
- In certain scenarios, it is necessary to handle multiple channels concurrently.
- The select statement provides an efficient way to handle multiple channels.
- When you need to wait on multiple channel operations, you need to use the `select` statement.
- Also allows for non-blocking channel operations (send/receive)

```go
select { 
    case <-ch1: // code to handle receive operation 
    case ch2 <- value: // code to handle send operation 
    default: // code to handle when no channel operation is ready 
}
```
---
#### Handling Multiple Channels

```go
c1 := make(chan string)
c2 := make(chan string)
go func() {
    time.Sleep(1 * time.Second)
    c1 <- "one"
}()
go func() {
    time.Sleep(2 * time.Second)
    c2 <- "two"
}()
for i := 0; i < 2; i++ {
    select {
    case msg1 := <-c1:
        fmt.Println("received", msg1)
    case msg2 := <-c2:
        fmt.Println("received", msg2)
    }
}
```

---
#### Using Timeouts with select
- Timeouts are crucial in channel operations to prevent indefinite blocking.
- `time.After` function returns a channel that sends a value after a specified duration.
```go 
select { 
    case <-ch: // code to handle receive operation 
    case <-time.After(timeout): // code to handle timeout 
}
```

---
#### Using Timeouts with Select (cont.)

```go
select {
case <-ch1:
    fmt.Println("Received data from Worker 1")
case <-time.After(3 * time.Second):
    fmt.Println("Timeout! Worker 1 took too long to respond")
}
```

---
# Try it out 🏋️‍♀️

```shell
cd 100-concurrency/70-select-statement-and-timeouts
go run select-statement-n-timeouts.go
```
{{% /section %}}