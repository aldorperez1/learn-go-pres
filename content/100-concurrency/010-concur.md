+++
+++

{{% section %}}
# Concurrent Programing

---

### What is Concurrency
- The ability of a program to execute multiple tasks simultaneously, making progress on multiple fronts.
- Done by dividing the program into smaller tasks that can run independently of each other
- E.g. A word processor that can spell-check and grammar-check a document while the user is typing.
- Why?
  - Make a program faster
  - Make a program more responsive

---
### Benefits of Concurrent Programs
- Efficiency and Performance
    - Utilizing multiple processor cores
    - Responsiveness
  - Improved User Experience
    - Parallelism
    - Asynchronous Operations
- Improved Scalability

---
### Challanges of Concurrent Programming
- Concurrency bugs
- Data races
- Syncronization
- Harder to write and understand

---
### Definition: Concurrency vs Parallelism

**Parallelism**
- Simultaneous execution of tasks on separate processors.
- Allows tasks to run at the same time

**Concurrency**
- Where two or more tasks can be in progress simultaneously
- Tasks take turns on a processor

---


<img src="/images/100-10-conc-v-parallel.webp"  >

---
#### Concurrent Programming in Go

- Go offers robust support for concurrent programming.
- Key features for concurrency in Go:
  - Goroutines: Lightweight, independently executing functions.
  - Channels: Typed communication channels for synchronization and data sharing.
  - Select statement: Handling multiple channel operations simultaneously.


{{% /section %}}