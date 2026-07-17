# Operating Systems — Interview Preparation Guide

*★ Starred items = most frequently asked / highest priority. Go through everything at least once, but if short on time, prioritize the starred ones.*

---

## Suggested Day-by-Day Study Plan (7-day moderate pace)

*~2-3 hrs/day. Adjust pacing based on how comfortable you already are with OS concepts.*

| Day | Focus |
|---|---|
| 1 | Process & Thread fundamentals + CPU Scheduling |
| 2 | IPC + Synchronization (mutex, semaphore, spinlock, classic problems) |
| 3 | Deadlocks (conditions, prevention/avoidance/detection, Banker's Algorithm) |
| 4 | Memory Management (paging, segmentation, fragmentation, TLB) |
| 5 | Page Faults & Thrashing (replacement algorithms, Belady's Anomaly) |
| 6 | System Calls, kernel mode, and misc/rapid-fire topics |
| 7 | Full revision — go through only the starred questions, out loud, like a mock interview |

---

## Topics to Cover Before the Interview

### 1. Process & Thread Fundamentals
- ★ What is a process vs a thread
- Process Control Block (PCB)
- ★ Process states (New, Ready, Running, Waiting, Terminated)
- Process lifecycle / state transition diagram
- ★ Multi-process vs multi-threading (trade-offs)
- ★ Context switching — what happens, and its cost
- User-level threads vs kernel-level threads
- Thread pools
- ★ Concurrency vs parallelism

### 2. CPU Scheduling
- ★ Scheduling algorithms: FCFS, SJF, SRTF, Round Robin, Priority, Multilevel Queue/Feedback Queue
- ★ Preemptive vs non-preemptive scheduling
- Convoy effect
- Turnaround time, waiting time, response time (definitions & calculations)
- Context switch overhead in scheduling

### 3. Inter-Process Communication (IPC)
- ★ Shared memory vs message passing
- Pipes, named pipes (FIFOs), message queues, sockets
- Signals

### 4. Synchronization
- Critical Section problem
- ★ Race conditions
- ★ Mutex vs Semaphore vs Spinlock
- ★ Binary semaphore vs mutex (subtle difference)
- Counting semaphore
- Monitors
- ★ Classic problems: Producer-Consumer, Dining Philosophers, Readers-Writers
- Priority inversion
- Busy waiting

### 5. Deadlocks
- ★ Four necessary conditions (mutual exclusion, hold & wait, no preemption, circular wait)
- ★ Deadlock prevention vs avoidance vs detection vs recovery
- ★ Banker's Algorithm (concept + basic trace)
- Resource Allocation Graph
- ★ Deadlock vs livelock vs starvation

### 6. Memory Management
- Contiguous memory allocation
- ★ Paging vs Segmentation
- Page table, multilevel paging
- ★ TLB (Translation Lookaside Buffer) and why it helps
- ★ Internal vs external fragmentation
- ★ Virtual memory concept
- Swapping

### 7. Page Faults & Thrashing
- Demand paging
- ★ Page fault — what happens step by step
- ★ Page replacement algorithms: FIFO, LRU, Optimal, LFU
- ★ Belady's Anomaly
- ★ Thrashing — cause and fix (working set model)

### 8. System Calls & Kernel
- ★ What is a system call, and examples (fork, exec, wait, read, write)
- ★ User mode vs Kernel mode, and mode switching
- System call vs library function call
- Monolithic vs Microkernel (basic awareness)
- Interrupts vs system calls

### 9. Miscellaneous / Good to Know
- Cache basics, cache coherence (if systems-heavy role)
- File systems basics (inode, file allocation table) — light touch
- Booting process overview
- Zombie process vs orphan process
- fork() vs exec() vs vfork()

---

## Full Interview Question Bank

*Starred (★) questions are the ones that come up most often across companies — make sure you can answer these confidently and quickly.*

### Process vs Thread
- ★ What is the difference between a process and a thread?
- ★ Why are threads called "lightweight" processes?
- What is stored in a Process Control Block (PCB)?
- ★ What are the different states a process can be in? Draw the transition diagram.
- ★ What happens during a context switch? Why is it expensive?
- ★ Multi-process vs multi-threaded architecture — when would you choose one over the other?
- What is a thread pool and why is it used?
- Difference between user-level and kernel-level threads
- ★ Concurrency vs Parallelism — explain with an example
- ★ Can a single-core CPU run multiple threads in parallel? (Trick question — no, only concurrently)
- What is a daemon thread?
- What is the difference between a zombie process and an orphan process?

### CPU Scheduling
- What is CPU scheduling and why is it needed?
- ★ Explain FCFS, SJF, SRTF, Round Robin, and Priority scheduling
- What is the Convoy effect and which algorithm suffers from it?
- ★ Preemptive vs non-preemptive scheduling — give examples of each
- How do you choose a time quantum in Round Robin? What happens if it's too small/large?
- ★ What is starvation in scheduling and how is it solved (aging)?
- Difference between turnaround time, waiting time, and response time
- What is a Multilevel Feedback Queue?

### Inter-Process Communication
- What is IPC and why do processes need it?
- ★ Compare shared memory and message passing — which is faster and why?
- What is a pipe? Difference between a pipe and a named pipe (FIFO)?
- When would you use sockets over shared memory?
- What is a message queue?
- What are signals in an OS?

### Synchronization
- ★ What is a race condition? Give a real example.
- ★ What is the Critical Section problem? What are its three requirements (mutual exclusion, progress, bounded waiting)?
- ★ Difference between Mutex and Semaphore
- ★ Difference between binary semaphore and mutex — aren't they the same?
- ★ What is a spinlock? When is it preferred over a mutex?
- What is busy waiting and how do you avoid it?
- ★ Explain the Producer-Consumer problem and how semaphores solve it
- ★ Explain the Dining Philosophers problem and how it's solved
- Explain the Readers-Writers problem
- What is a monitor? How is it different from a semaphore?
- What is priority inversion? How is it solved (priority inheritance)?
- Can a deadlock occur with just one semaphore?

### Deadlocks
- ★ What is a deadlock?
- ★ What are the four necessary conditions for deadlock?
- ★ Difference between deadlock prevention, avoidance, detection, and recovery
- ★ Explain the Banker's Algorithm
- What is a Resource Allocation Graph and how does it help detect deadlocks?
- ★ Difference between deadlock and starvation
- ★ Difference between deadlock and livelock
- How would you recover from a deadlock once it happens?
- Can a system with a single instance of each resource type have circular wait without deadlock?

### Memory Management
- ★ What is the difference between paging and segmentation?
- ★ What is internal fragmentation vs external fragmentation?
- What is a page table? What does each entry contain?
- ★ What is a TLB and why does it speed things up?
- Why is multilevel paging used instead of a single-level page table?
- ★ What is virtual memory and why do we need it?
- What is the difference between logical address and physical address?
- What is swapping?
- How does the OS handle a very large process that doesn't fit in physical memory?

### Page Faults & Thrashing
- ★ What is a page fault? Walk through what happens when one occurs.
- What is demand paging?
- ★ Explain FIFO, LRU, and Optimal page replacement algorithms
- ★ What is Belady's Anomaly? Which algorithm can suffer from it?
- ★ What is thrashing? What causes it and how do you fix it?
- What is the working set model?
- Compare LRU vs Optimal — why is Optimal not practical?

### System Calls & Kernel Mode
- ★ What is a system call? Give examples.
- ★ Difference between user mode and kernel mode
- ★ What happens during the transition from user mode to kernel mode?
- Difference between a system call and a normal library function call
- What is the difference between an interrupt and a system call?
- ★ Explain fork(), exec(), and wait() system calls
- Difference between fork() and vfork()
- What is a trap?

### General / Rapid-Fire (commonly opens the OS round)
- ★ What is an operating system and what are its main functions?
- What is the difference between a monolithic kernel and a microkernel?
- ★ What is virtualization? Difference between a VM and a container?
- What is the difference between multitasking, multiprogramming, and multiprocessing?
- What is a real-time operating system?
- What is the boot process of an OS (high level)?
- What is cache memory and why is it faster than RAM?
- Explain the difference between a hard link and a soft link (file systems).

---

**Tip:** For every starred question, be ready to also give a real-world example or a one-line code/pseudocode sketch (e.g., semaphore code for Producer-Consumer) — interviewers often ask a follow-up "can you show me how you'd implement this?"
