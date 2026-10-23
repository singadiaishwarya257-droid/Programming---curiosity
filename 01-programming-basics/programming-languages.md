# Programming languages

A programming language is a notation for describing operations and decisions in a form people can write and computers can execute. Different languages make different trade-offs in readability, performance, safety, and the kinds of tasks they make convenient.

For example, both snippets display a message:

```python
print("Hello!")
```

```javascript
console.log("Hello!");
```

The ideas are similar, but the syntax and surrounding tools differ.

## How languages relate to computers

Processors execute low-level machine instructions. Most programmers use higher-level languages instead, then rely on a compiler or runtime to translate or execute the program. This lets people express larger ideas without manually writing processor instructions.

Languages are often described as:

- **Compiled:** source code is translated ahead of execution, often into machine code or another representation.
- **Interpreted:** a runtime reads or executes the program as it runs.
- **Statically typed:** many type mistakes can be detected before the program runs.
- **Dynamically typed:** types are commonly checked during execution.

These labels are useful, but implementations often combine approaches. A language is not inherently “better” because it has one label. Choose based on the task, ecosystem, team, and constraints. Compare [Python](../09-language-comparisons/python.md), [JavaScript](../09-language-comparisons/javascript.md), and [Java](../09-language-comparisons/java.md).

## Curiosity questions

3. Why can't humans directly communicate with a computer?
4. How does a computer understand `if`, `for`, `while`, and `function`?
5. Who decides what a programming language can do?
6. Why are there hundreds of programming languages?
7. Why do we need Python, Java, JavaScript, C, C++, Go, Rust, and others?
8. What makes one programming language different from another?

## Explanations guided by the seven questions

### 3. Why can't humans directly communicate with a computer?

Human language is flexible and often ambiguous; machines need precise operations. Computers ultimately execute encoded machine instructions. Compilers and runtimes translate human-written code into executable operations. Translation happens in development tools and language runtimes. It happens before or during program execution. Language implementers build translators; programmers use them. A translator cannot resolve unclear intent and may reject or misinterpret invalid code.

### 4. How does a computer understand `if`, `for`, `while`, and `function`?

These constructs express decisions, repetition, and reusable operations. They are syntax with defined meaning in a language. A compiler or interpreter parses them into control-flow operations. Their behavior is implemented in the language toolchain and runtime. Conditions and loops take effect as execution reaches them. Language designers define semantics; implementers encode them. Invalid syntax is rejected; faulty logic can still run incorrectly.

### 5. Who decides what a programming language can do?

A language needs coherent rules so tools and programmers can rely on it. Its specification, implementation, libraries, and runtime determine available features. Language communities, standards bodies, and implementers propose and adopt changes. Decisions appear in specifications, compiler releases, and library APIs. Features change through versioned proposals and releases. The decision-maker varies by language: it may be a standards group, foundation, vendor, or community. Different implementations may support features at different times.

### 6. Why are there hundreds of programming languages?

Different problems, platforms, and eras create different design needs. Languages are alternative ways to express computation. Designers choose different trade-offs in safety, speed, syntax, and abstraction. Languages serve web, systems, data, embedded, scientific, and other domains. A new language is useful when its benefits justify adoption and maintenance costs. Researchers, companies, communities, and standards groups create languages. Too many choices can fragment tools and expertise.

### 7. Why do we need Python, Java, JavaScript, C, C++, Go, Rust, and others?

No single language optimizes every goal and environment. Each offers a different mix of runtime, ecosystem, and programming model. Teams select a language whose strengths fit the product and constraints. Their typical domains overlap; they are not limited to one use. Choose after considering platform, performance, safety, libraries, and team skills. Developers and organizations make the choice. A poor fit can increase cost, complexity, or operational risk.

### 8. What makes one programming language different from another?

Different designs make different kinds of work easier or safer. Syntax, semantics, type systems, runtimes, libraries, and tooling vary. Those choices affect how code is written, checked, executed, and maintained. Differences appear in source code, build tools, runtime behavior, and ecosystem. They matter during development, deployment, debugging, and scaling. Language designers define them; programmers experience their trade-offs. Similar-looking code can behave differently across languages.
