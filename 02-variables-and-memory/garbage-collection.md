# Garbage collection

Garbage collection (GC) is automatic memory management: a runtime identifies objects that a program can no longer reach and reclaims their storage so it can be reused.

## Reachability

Imagine a program has a list of objects. Objects reachable from active variables or other live objects may still be needed. Objects with no path from those roots are candidates for collection. A common collector traces reachable objects and reclaims the rest.

```text
active variable -> object A -> object B
                  object C (unreachable)
```

Objects A and B are reachable through the active variable. C may be collected.

## Benefits and trade-offs

GC can prevent many bugs caused by freeing memory too early or forgetting to free it. It does not mean memory is unlimited: a program can accidentally keep references to data it no longer needs, so that data remains reachable. Collection also consumes CPU time and may affect pause times, although modern runtimes use different strategies to manage this.

Some languages rely mainly on garbage collection; others use ownership rules, reference counting, or explicit allocation and deallocation. Even in a GC language, closing files, network connections, and other external resources is usually the program's responsibility. Compare [stack and heap](stack-and-heap.md) for how data is commonly organized.

## Curiosity questions

20. Who cleans unused memory?
28. What is garbage collection?
29. Why doesn't unused memory remain forever?

## Explanations guided by the seven questions

### 20. Who cleans unused memory?

Reclaiming unreachable storage lets a process reuse limited memory. Cleanup may be automatic garbage collection or explicit deallocation. Runtimes trace references, count ownership, or follow language-specific rules. Memory managers operate within the process and runtime. Cleanup occurs when data is no longer needed, sometimes later than it becomes unused. A garbage collector, allocator, or programmer-managed ownership system. A lingering reference prevents collection even when the data is logically unwanted.

### 28. What is garbage collection?

It reduces the need for programmers to manually free every object. GC is automatic reclamation of objects the program can no longer reach. Collectors identify reachable objects and reuse storage occupied by the rest. It runs as part of a language runtime. Timing and frequency depend on memory pressure and collector strategy. The runtime performs collection; programmers still manage external resources. GC cannot reclaim objects that the program accidentally keeps reachable.

### 29. Why doesn't unused memory remain forever?

Reusing memory allows programs to continue within finite resources. Reclaimable storage is returned to an allocator for future use. A collector or explicit deallocator marks memory reusable. It may return to the process allocator before the OS gets it back. Reclamation timing varies; it is not always immediate. The runtime and operating system manage different levels of reclamation. A leak or retained reference can keep memory occupied.
