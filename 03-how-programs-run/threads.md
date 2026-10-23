# Threads

A thread is a sequence of instructions that an operating system or runtime can schedule to run. A process can contain one thread or many. Threads in one process typically share its memory and other resources.

## Why use multiple threads?

Multiple threads can keep an application responsive while background work continues, or allow work to run in parallel on multiple processor cores. Whether they improve performance depends on the task, hardware, runtime, and amount of coordination required.

## Shared state needs care

If two threads update the same data at the same time, the result can depend on timing. This is a race condition. Locks, message passing, atomic operations, and other synchronization tools can help, but incorrect coordination can cause bugs such as deadlocks.

Not every language or runtime maps its concurrency features directly to operating-system threads. Some use event loops, lightweight tasks, or other models. Concurrency means multiple tasks make progress over overlapping time; parallelism means tasks literally execute at the same time. They are related but not identical. See [processes](process.md) for the larger execution boundary.

## Curiosity questions

34. What is a thread?

## Explanations guided by the seven questions

### 34. What is a thread?

Threads let a process organize and overlap multiple paths of work. A thread is a schedulable sequence of execution within a process. The OS or runtime schedules its instructions on available processor cores. It shares a process's address space and many resources. A program uses threads for concurrency or parallel work. The OS and runtime schedule them; the application creates or coordinates them. Unsynchronized shared state can create races or deadlocks.
