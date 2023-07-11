+++
+++

{{% section %}}


# Channels 📺

---
#### What are channels and what do they help me do?
- Channels allow you to send information between goroutines
- Channels facilitate communication and synchronization between goroutines.
- Safe and efficient way to exchange data in Go.

---
#### Creating Channels
- Channels are created using the `make` function.
- Syntax: `make(chan <type>)`

```go
ch := make(chan int) // Only integers allowed into channel
```

---
#### Channel Operations
Sending Data
```go
mychannel <- 2
```
Receiving Data

```go
value := <- channel
```
Closing Channels

```go
close(channel)
```

---
#### Iterating Over a Channel

- Iterating over a channel allows us to process all the values it receives until the channel is closed.
- We can use a `for` loop with a range clause to iterate over the channel.

---

```go
ch := make(chan int)
go func() {
	for i := 1; i <= 5; i++ {
		ch <- i // Sending values to the channel
	}
	close(ch) // Closing the channel
}()
// Iterating over the channel using a for loop
for value := range ch {
	fmt.Println("Received value:", value)
}
```
- The loop will continue until the channel is closed and all values have been received.

{{% note %}}
Explanation:
- In this example, we create an integer channel `ch`.
- A goroutine is launched to send the values 1 to 5 to the channel.
- After sending all the values, we close the channel using `close(ch)`.
- Using a `for` loop with the `range` clause, we iterate over the channel.
- The loop automatically receives values from the channel until it is closed.
- Each received value is printed to demonstrate the iteration process.

{{% /note %}}



---
#### Channel Buffering and Blocking
- Unbuffered Channels: Synchronous communication, blocks sender and receiver until both are ready.
- Buffered Channels: Capacity allows buffering of values. Sender blocks only when the channel is full, receiver blocks only when the channel is empty.
---
#### Example of Buffered Channel

```go
bufferedCh := make(chan string, 2) // Buffered channel with capacity 2

bufferedCh <- "Hello" // Sending data without blocking
bufferedCh <- "World"

// Uncomment the line below to demonstrate blocking behavior
// bufferedCh <- "Blocked"

fmt.Println("Buffered channel values:")
fmt.Println(<-bufferedCh) // Receiving buffered values
fmt.Println(<-bufferedCh)

// Uncomment the line below to demonstrate blocking behavior
// fmt.Println(<-bufferedCh)
```
Try it yourself.
```shell
go run 100-concurrency/60-channels/BufferedChan/bufferedchannel.go
```

---
#### Unidirectional Channel Types
- Increase type safety to channels by specifying channel types
- Stops users from using the channel the wrong way

Bidrectional
```go
bidir := make(chan int)
```

Send-only

```go
sendOnlyCh := make(chan<- int)
```
Receive-only

```go
receiveOnlyCh := make(<-chan int)
```

---
#### Example of Channel types
The following will not compile since the channels are not being used correctly

```go
sendOnlyCh := make(chan<- int) // Send-only channel
receiveOnlyCh := make(<-chan int) // Receive-only channel
// the following will fail to compile
receiveOnlyCh <- 10 // Trying to send a value to a receive only
fmt.Println(<-sendOnlyCh) // Trying to receive from a send only channel
```
---
# Exercise 🏋️‍♀️

Run this program it first
```shell
go run channel-direction.go
```
It runs. Now try to make the compiler fail by using a restricted channel wrong.


---
#### Channel Syncronization

Channels can be used to syncronize execution across goroutines
```go
func worker(done chan bool) {
    fmt.Print("working...")
    time.Sleep(time.Second)
    fmt.Println("done")
    done <- true
}
func main() {
    done := make(chan bool, 1)
    go worker(done)
    <-done
}
```
Try it yourself. 
```shell
go run 100-concurrency/60-channels/channelSync/channel-sync.go 
```

---
### Select
{{% /section %}}