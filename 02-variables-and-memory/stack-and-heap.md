# Stack and heap

The **stack** and **heap** are common terms for areas used to manage a program's working data. They describe broad allocation patterns, not two universally identical physical regions; implementations vary by language, compiler, and operating system.

## The stack

When a function is called, the program needs to remember information such as where to return and which local values it is using. This call information is often managed in stack frames. Returning from a function usually removes its frame.

```text
main() calls calculate()
  calculate() uses its own call frame
calculate() returns
  its call frame is no longer needed
```

Deep or endless recursion can use too many call frames and lead to a stack overflow.

## The heap

The heap is commonly used for data whose size or lifetime is not tied to a single function call, such as objects shared across functions. Heap allocation is flexible, but it requires a way to determine when data is no longer needed. Some languages use garbage collection; others require explicit ownership or deallocation.

These are useful mental models, not strict rules that every local variable lives on the stack and every object lives on the heap. Compilers can optimize storage, and language semantics matter more than a simplistic diagram. See [memory](memory.md) and [garbage collection](garbage-collection.md).

## Curiosity questions

19. What happens to variables when a function finishes?
26. What is a stack?
27. What is a heap?

## Explanations guided by the seven questions

### 19. What happens to variables when a function finishes?

Function-local state should usually stop being accessible after the call. Local bindings leave scope, but referenced objects may continue to exist. The runtime discards or clears the call's local frame or scope. Bindings and objects are in the process's managed memory. Scope ends when the function returns or unwinds with an error. The runtime manages local scope and memory lifetime. A returned or captured reference can keep an object alive.

### 26. What is a stack?

Programs need to track nested function calls and their return points. A stack is a last-in, first-out structure often used for call frames. A call adds a frame; returning removes it. It is part of the process's execution state, with implementation-specific layout. It is used as functions call one another. Compiler, runtime, and processor conventions manage it. Excessive recursion or large stack use can cause stack overflow.

### 27. What is a heap?

Some data must outlive a function call or be shared flexibly. The heap is a managed region or allocation model for dynamic data. Runtime allocators provide storage and later reclaim or reuse it. It is part of a process's virtual memory, though exact layout varies. It is useful when data lifetime is not tied to one call frame. The runtime, allocator, or programmer manages allocations. Poor lifetime management can cause leaks, fragmentation, or allocation failures.
