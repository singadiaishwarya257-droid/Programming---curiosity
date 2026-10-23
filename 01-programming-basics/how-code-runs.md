# How code runs

Code starts as text written in a programming language. To run it, your computer needs a toolchain that can turn that text into operations the processor can carry out.

## A simplified path

1. You write source code and save it in a file.
2. A compiler, interpreter, or runtime checks and processes the code.
3. The operating system starts a program and gives it resources such as memory and access to files.
4. The processor executes instructions, while the program may ask the operating system or other services to do work.
5. The program produces results: perhaps text, a changed file, a web page, or a response to another program.

The details depend on the language. A C program is commonly compiled into a native executable. Python source is typically run by a Python interpreter. Java source is commonly compiled to bytecode, then run by the Java Virtual Machine.

## A tiny example

When a program prints `Hello`, it does not usually draw letters directly on a screen. It asks a library or runtime to send output to a terminal or other destination. The operating system and device drivers help connect that request to the physical display.

Errors can occur at different stages: a syntax error while processing the code, a runtime error while executing it, or a logic error when it runs but gives the wrong result. Explore [compilers](../03-how-programs-run/compiler.md), [interpreters](../03-how-programs-run/interpreter.md), and [processes](../03-how-programs-run/process.md) for more detail.

## Curiosity questions

10. What actually happens when you run a program?

## Explanations guided by the seven questions

### 10. What actually happens when you run a program?

Running turns a written program into actions and observable results. A runtime or operating system starts instructions with input and resources. Tools process code; the OS creates a process; the processor executes operations. Execution occurs on a device or server, often with remote services involved. It begins when you launch a command, app, job, or service. The operating system, runtime, processor, libraries, and program all participate. Errors may occur during parsing, execution, I/O, or logic.
