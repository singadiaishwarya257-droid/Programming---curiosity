# Interpreters

An interpreter is a program that executes instructions from another program. It may read source code directly, execute bytecode, or use a mixture of interpretation and compilation.

For example, running a Python script usually starts the Python runtime, which processes the script and carries out its operations. The runtime also provides services such as objects, memory management, and built-in functions.

## Interpreter and compiler are not opposites

It is common to describe languages as either “compiled” or “interpreted,” but these terms describe implementation techniques. A runtime can compile source to bytecode, interpret that bytecode, and JIT-compile frequently used parts. A compiled program can also rely on an interpreter or virtual machine at runtime.

An interpreter can make interactive development convenient and help a language run on different systems that have compatible runtimes. Performance and startup time depend on many factors, not simply the label “interpreted.”

An interpreter does not automatically make code safe: it still needs sensible permissions and input handling. For related concepts, read [compilers](compiler.md) and [processes](process.md).

## Curiosity questions

35. Where does the Python interpreter run?
36. How does Python read your `.py` file?
37. Does Python directly understand your source code?
38. What is bytecode?
39. What is the Python Virtual Machine?

## Explanations guided by the seven questions

### 35. Where does the Python interpreter run?

Python code needs a runtime to execute its language semantics. The interpreter is itself a native program running on the operating system. The OS loads the interpreter as a process; it processes Python instructions. On the local device, server, or embedded system where Python is installed. It starts when a Python command or application launches it. The OS schedules it; Python's runtime executes the script. A missing or incompatible interpreter prevents the script from running.

### 36. How does Python read your `.py` file?

The runtime needs the source instructions to execute the program. It reads text, parses Python syntax, and usually compiles it to bytecode. The interpreter tokenizes and parses source, then evaluates or executes compiled code. The file is read from storage into the interpreter process. Usually at startup or when a module is imported. Python's interpreter and import system perform these steps. Invalid syntax or inaccessible files produce an error before the intended code runs.

### 37. Does Python directly understand your source code?

Source must be processed into operations the runtime can execute. Python's implementation parses source and commonly compiles it to bytecode. The virtual machine executes bytecode while runtime services handle objects and operations. Processing occurs inside the Python interpreter process. It happens when a script or module is loaded. The interpreter performs the translation and execution. Python versions or implementations can differ in internal details.

### 38. What is bytecode?

An intermediate form can simplify execution across supported systems. Bytecode is a compact instruction representation for a virtual machine. A language implementation compiles source into instructions the VM understands. It may exist in memory or cached files such as Python's `.pyc` files. It is produced when Python compiles a module. The Python compiler creates it; the virtual machine executes it. Bytecode compatibility is implementation- and version-dependent.

### 39. What is the Python Virtual Machine?

It provides a consistent execution model for Python bytecode. It is the bytecode execution engine inside a Python implementation. It steps through bytecode instructions and invokes runtime operations. It runs as part of the interpreter process. It is active while Python code executes. The Python implementation supplies the VM. Other Python implementations can use different internal execution engines.
