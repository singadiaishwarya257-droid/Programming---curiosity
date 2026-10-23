# Python

Python is a general-purpose programming language known for readable syntax and a large ecosystem of libraries. It is commonly used for automation, data analysis, scientific computing, web services, and education.

```python
names = ["Ada", "Grace"]
for name in names:
    print(f"Hello, {name}!")
```

Python uses dynamic typing: values have types, and many type checks happen while the program runs. Optional type annotations can help tools and readers understand expected data, but they do not normally change Python's runtime behavior by themselves.

The Python interpreter and its ecosystem make it easy to experiment, though performance depends on the workload and implementation. Many demanding tasks use optimized libraries or other runtimes under the surface.

Python is a strong choice when clarity, fast iteration, or its libraries suit the problem. It is not automatically the best language for every application. Compare [JavaScript](javascript.md), [Java](java.md), and [all three](python-vs-javascript-vs-java.md).

## Curiosity questions

81. Why is Python popular for AI?
89. Can Python call code written in C?

## Explanations guided by the seven questions

### 81. Why is Python popular for AI?

It enables quick experimentation and access to mature AI libraries. Python is often the interface to optimized numerical and machine-learning engines. Libraries call native code, accelerators, and distributed systems beneath Python APIs. Used in research notebooks, data pipelines, and production services. It is useful when ecosystem and development speed outweigh runtime constraints. Researchers, data scientists, and engineers use it. Pure Python may be slow for intensive computation; optimized libraries address many such workloads.

### 89. Can Python call code written in C?

Native libraries can provide speed or reuse existing C functionality. Python can invoke C through extension modules or foreign-function interfaces. Bindings convert arguments and results across the language boundary. The C library and Python runtime load in the same process in common approaches. Use it when profiling justifies native code or a needed library is available. Extension authors define and maintain the binding. Incorrect memory handling or type conversion can crash the process.
