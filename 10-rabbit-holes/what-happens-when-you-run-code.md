# What happens when you run code?

Running a program involves several layers between the source file and the result you see.

1. **You request execution.** A terminal, editor, or operating system starts the appropriate tool.
2. **The language tool processes the source.** A compiler or interpreter checks and translates the code as required.
3. **The operating system creates a process.** It assigns resources and establishes the process's permissions and environment.
4. **The processor executes instructions.** The program reads data, performs calculations, and may make requests to the operating system.
5. **Libraries and services do their work.** A program might display output, read a file, contact a database, or send a network request.
6. **The program finishes or keeps running.** Its exit status and output can be inspected; the operating system reclaims process resources when it ends.

These steps are a mental model, not a universal fixed pipeline. A runtime may compile code during execution, and a program may launch other processes or communicate with remote services. Bugs can come from source syntax, runtime state, operating-system permissions, or incorrect assumptions about the problem.

Related topics: [how code runs](../01-programming-basics/how-code-runs.md), [compilers](../03-how-programs-run/compiler.md), [interpreters](../03-how-programs-run/interpreter.md), and [processes](../03-how-programs-run/process.md).

## Curiosity question

When you type `python app.py`, what happens between pressing Enter and seeing the output?

## Explanations guided by the seven questions

### Rabbit hole: What happens between typing `python app.py` and seeing output?

The command asks the computer to execute a Python program. Shell, OS, interpreter, script, libraries, and output device take part. The shell resolves Python; the OS starts it; Python loads and runs the script. Processes run on the local machine or selected remote environment. Output appears after the relevant code executes and writes it. Shell, operating system, Python runtime, program, and terminal cooperate. Syntax, dependency, permission, or runtime errors can stop the path at different stages.
