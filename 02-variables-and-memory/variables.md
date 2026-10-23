# Variables

A variable is a name a program uses to refer to a value. Instead of repeating the same value throughout a program, you can give it a meaningful name and use that name in calculations or decisions.

```python
price = 12
quantity = 3
total = price * quantity
```

Here, `price`, `quantity`, and `total` are names. The value of `total` is calculated from the other two.

## Names and values

A variable is not always a literal box containing its value. Depending on the language and value, a name may refer to data stored elsewhere in memory. Assigning a new value can update the binding, and assigning a mutable object to another variable may make both names refer to the same object.

```python
first = [1, 2]
second = first
second.append(3)
print(first)  # [1, 2, 3]
```

Understanding this distinction helps avoid surprising changes. A variable's **scope** describes where its name can be used. Its **lifetime** describes how long the associated value remains available. Languages differ in how they declare variables and check their types. For the underlying storage concepts, see [memory](memory.md) and [stack and heap](stack-and-heap.md).

## Curiosity questions

11. What happens internally when you write `x = 10`?
13. Where is `x` stored?
14. Is `x` actually the value `10`?
15. What happens when you write:

    ```python
    x = 10
    x = 20
    ```

16. What happens to `10`?
17. What happens when you write `a = b = c = 100`?
18. Are `a`, `b`, and `c` three copies of `100`?
23. Where does a Python variable live?
24. What is a memory address?
25. Why can't we normally see memory addresses in Python?

### Rabbit hole

When you type `x = 10`, where exactly does `10` go? Follow the chain: **Variable → Object → Memory → RAM → Process → OS**.

## Explanations guided by the seven questions

### 11. What happens internally when you write `x = 10`?

Assignment gives a value a usable name. The name `x` is bound to the integer value `10`. The language runtime evaluates the literal and records the binding. The name and object are represented in the running process's memory. The binding changes when that statement executes. The language runtime performs the assignment. A later assignment can bind `x` to a different value.

### 13. Where is `x` stored?

The program must keep track of names and their values. `x` is a name in a scope, not necessarily a physical box. The compiler or runtime maps the name to a local, global, or object binding. Its representation is in the process's memory; exact placement is implementation-dependent. The binding exists while its scope and lifetime permit access. The language implementation and operating system manage the representation. Optimization can change physical placement without changing language behavior.

### 14. Is `x` actually the value `10`?

Distinguishing names from values explains reassignment and sharing. `x` is a name that refers to or is bound to a value. Assignment creates or updates a binding according to language rules. The name belongs to a scope; the value is represented in memory. The relationship applies while the binding remains unchanged. The runtime enforces that relationship. Reassigning `x` changes its binding, not necessarily every reference to the old value.

### 15. What happens when you write `x = 10` followed by `x = 20`?

Reassignment lets a program update its working state. `x` first refers to 10, then is rebound to 20. Each statement executes in order and updates the binding. The binding is in the current scope of the running process. The second assignment takes effect when execution reaches it. The language runtime performs both assignments. Another name still referring to 10 may keep that value alive.

### 16. What happens to `10`?

Values remain available only while a program can still use them. The old integer may become unreachable after `x` is rebound. Reference tracking or garbage collection determines whether it can be reclaimed. Its storage is managed within the process and runtime. Reclamation may happen later, not necessarily immediately. The runtime or memory manager reuses reclaimable storage. If another reference exists, the value remains available.

### 17. What happens when you write `a = b = c = 100`?

Chained assignment provides a concise way to bind several names. Each name is assigned the result of the right-hand expression. The expression is evaluated and assignment proceeds according to the language's rules. Each name is bound in its applicable scope. The names are assigned when the statement executes. The language runtime applies the assignment semantics. For mutable values, shared references can make changes visible through multiple names.

### 18. Are `a`, `b`, and `c` three copies of `100`?

Knowing whether values are copied or shared helps predict behavior. In Python, the names bind to the same integer object where object identity is relevant. Assignment binds names; it does not promise to copy an object. The bindings exist in their scopes and the object in process memory. This matters especially when the assigned object is mutable. The language semantics and runtime determine object behavior. Reassigning a name does not reassign the other names; mutating a shared object can affect all references.

### 23. Where does a Python variable live?

A running program needs bindings to retrieve values by name. A Python variable is a name bound to an object, not a fixed memory cell. Python stores bindings in namespaces, local scopes, and object attributes. Those structures reside in the process's memory, with implementation-dependent placement. A binding is available while its scope and references remain active. The Python implementation and operating system manage it. The binding can disappear while the object survives through another reference.

### 24. What is a memory address?

Hardware and low-level software need a way to locate stored data. An address identifies a location in an address space. A process uses virtual addresses that the OS and hardware map to physical memory. Addresses refer to locations within a process or system address space. Programs use them during memory access, usually behind language abstractions. The processor, operating system, and runtime coordinate their use. Invalid access can cause errors or security problems.

### 25. Why can't we normally see memory addresses in Python?

Hiding raw addresses makes programs more portable and memory-safe. Python exposes object behavior rather than requiring manual address handling. The runtime manages object references and memory allocation. Low-level address details are internal to the implementation. Most ordinary application code does not need addresses. Python's implementation abstracts them from programmers. Specialized debugging tools or implementation-specific functions can reveal details, but those are not portable identifiers.

### Rabbit hole: When I type `x = 10`, where exactly does `10` go?

The program needs to represent the integer so later operations can use it. Python evaluates `10` as an integer object and binds the name `x` to it. The interpreter creates or reuses the object and records the name in a namespace. The object and namespace are managed in the Python process's virtual memory; active pages are backed by RAM. This happens as the assignment statement executes. Python's runtime manages the object and binding; the OS manages the process's memory. Rebinding `x` can make the old object reclaimable, unless another reference still points to it.
