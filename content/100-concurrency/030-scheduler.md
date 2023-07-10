+++
+++

{{% section %}}

{{< slide id="scheduler" >}}
# The go scheduler
Takes care of scheduling the goroutine to run. Otherwise, it would never run 😅

---
#### The go scheduler

- Schedules/runs created go routines
- Pausing and resuming them
- blocking channel operations or mutex operations
- Coordinates
  - Blocking system calls
  - Network i/o
  - garbage collector 
- It does this for hundreds of thousands of goroutines
- Runs when goroutines cede control e.g. create a new goroutine, block

---
#### What happens once the `go` command is executed?

- Once a goroutine is created, the main goroutine stops and cedes control to the go scheduler.
- The go scheduler will multiplex it to a small number of threads
- The scheduler will try to find an idle existing thread or else create a new one.
- It will schedule the goroutine to run on that thread
- Once the scheduling done, it returns to whatever it was doing.

---
### Goroutine Scheduler - (1/12)

<img src="/images/100-30-scheduler-01.png">

---
### Goroutine Scheduler - (2/12)

<img src="/images/100-30-scheduler-02.png">

---
### Goroutine Scheduler - (3/12)

<img src="/images/100-30-scheduler-03.png">

---
### Goroutine Scheduler - (4/12)

<img src="/images/100-30-scheduler-04.png">

---
### Goroutine Scheduler - (5/12)

<img src="/images/100-30-scheduler-05.png">

---
### Goroutine Scheduler - (6/12)

<img src="/images/100-30-scheduler-06.png">

---
### Goroutine Scheduler - (7/12)

<img src="/images/100-30-scheduler-07.png">

---
### Goroutine Scheduler - (8/12)

<img src="/images/100-30-scheduler-08.png">

---
### Goroutine Scheduler - (9/12)

<img src="/images/100-30-scheduler-09.png">

---
### Goroutine Scheduler - (10/12)

<img src="/images/100-30-scheduler-10.png">

---
### Goroutine Scheduler - (11/12)

<img src="/images/100-30-scheduler-11.png">

---
### Goroutine Scheduler - (12/12)

<img src="/images/100-30-scheduler-12.png">

---
[Back to Home](..)
{{% /section %}}

