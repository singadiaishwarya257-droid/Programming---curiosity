# Compilers

A compiler translates source code into another form so it can be executed or processed. That output might be native machine code, bytecode for a virtual machine, or another intermediate representation.

## Typical stages

A compiler may:

1. Parse source text and check that it follows the language's grammar.
2. Analyze names, types, and other program rules.
3. Transform the program into an intermediate representation.
4. Optimize that representation.
5. Generate output for a target platform.

The actual pipeline differs between compilers. Some errors, such as a missing bracket or type mismatch, can be reported before execution. A program may still have logic errors or runtime failures after it compiles.

## Compilation and execution

With ahead-of-time compilation, much of the translation happens before the program starts. Other environments compile parts of a program during execution, sometimes using a just-in-time (JIT) compiler. Compiled output may be specific to an operating system or processor architecture.

Compilation is not the same as making a program correct or secure; it only transforms code and checks the rules the compiler knows about. See [interpreters](interpreter.md) and [how code runs](../01-programming-basics/how-code-runs.md).

## Curiosity questions

9. Why does a programming language need a compiler or interpreter?

## Explanations guided by the seven questions

### 9. Why does a programming language need a compiler or interpreter?

Processors execute machine instructions, not most human-friendly source code. A compiler or interpreter is a tool that processes a program's language. It parses and translates code, or executes its instructions through a runtime. It runs on a development machine, target device, or server. Translation may occur before execution, at startup, or during execution. Language implementers build it; developers run it. Without a compatible implementation, the source cannot run as intended.
