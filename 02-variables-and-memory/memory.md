# Memory

Memory is the computer's fast working space for data and instructions currently in use. When a program runs, it needs memory for values such as numbers, text, objects, and the state of its calculations. Unlike long-term storage such as an SSD, ordinary working memory is generally temporary: its contents are lost when power is removed.

## Addresses and data

Memory can be thought of as a large collection of locations, each with an address. Programs and runtimes use these locations to store and retrieve data. Modern operating systems give each process a virtual address space, so a program usually works with addresses that the operating system maps to physical memory.

Programmers typically do not choose physical memory locations themselves. The language runtime, compiler, and operating system manage the details. Some languages expose more control than others.

## Why memory matters

Programs can fail if they try to use invalid memory, or become slow if they use much more memory than needed. Memory leaks happen when a program retains data it no longer needs, preventing it from being reclaimed. Other common problems include unexpectedly sharing mutable data and accessing data after its lifetime.

The [stack and heap](stack-and-heap.md) are common ways to describe memory used by a running program, though their exact behavior depends on the language and runtime. [Garbage collection](garbage-collection.md) explains one way runtimes reclaim unused memory.

## Curiosity questions

12. Where is `10` stored?
21. What is RAM actually doing while your program runs?
22. What is the difference between RAM and storage?
30. What happens when your program consumes too much memory?

## Explanations guided by the seven questions

### 12. Where is `10` stored?

The program needs a representation of the value to use it. It is represented as data in the process's working memory when needed. The runtime allocates or reuses storage for the value. Ultimately in RAM while active, through virtual memory mappings. The representation exists while the runtime needs to retain it. The runtime and operating system manage its storage. The compiler or runtime may optimize constants, so there need not be one permanent location.

### 21. What is RAM doing while your program runs?

The processor needs fast access to instructions and active data. RAM holds working data and code currently in use. The OS maps process address spaces to physical memory pages. RAM is the computer's temporary main memory. It is used during execution and cleared when power is lost. The processor, memory controller, and operating system coordinate access. When physical RAM is pressured, the OS may reclaim caches or use slower virtual-memory mechanisms.

### 22. What is the difference between RAM and storage?

Computers need both fast temporary work space and durable data retention. RAM is volatile working memory; storage retains data without power. The OS loads data from storage into RAM for active processing. RAM is memory modules; storage is typically an SSD, hard drive, or remote service. RAM is used while programs run; storage preserves files between runs. Hardware and operating systems manage transfers between them. More RAM can reduce paging, but it does not replace persistent storage.

### 30. What happens when your program consumes too much memory?

Memory is finite and shared among processes. The process may slow down, fail an allocation, or be terminated. The OS may page memory or invoke resource limits and out-of-memory handling. Effects occur in the process and potentially across the system. It happens when demand exceeds available or permitted memory. The runtime, OS, and service supervisor may report or respond to it. Reduce retained data, stream work, optimize structures, or provision more memory after measuring.
