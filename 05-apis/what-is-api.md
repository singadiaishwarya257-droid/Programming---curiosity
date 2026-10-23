# What is an API?

An Application Programming Interface (API) is a defined way for one piece of software to interact with another. An API describes what operations are available, what inputs they accept, and what outputs or errors to expect.

An everyday analogy is a restaurant menu: it lists what you can request without explaining how the kitchen prepares it. A software API similarly lets a caller use a capability without knowing every internal detail.

## Different kinds of APIs

- A library API lets your code call functions provided by a package.
- An operating-system API lets programs request services such as opening files.
- A web API lets software communicate over a network, often using HTTP.

For example, a weather service might expose an operation that accepts a location and returns a forecast. The API's documentation should explain authentication, input formats, response structure, limits, and error behavior.

An API is a contract, not necessarily a particular technology. Read [request and response](request-response.md) for web exchanges and [REST APIs](rest-api.md) for one common web API design style.

## Curiosity questions

51. What exactly is an API?
52. Why can't two applications simply access each other's variables?

## Explanations guided by the seven questions

### 51. What exactly is an API?

Software needs defined ways to use another component's capabilities. An API is a contract describing available operations and their inputs and outputs. Callers use documented functions, protocols, or endpoints. APIs exist in libraries, operating systems, services, and devices. Use an API when components need a supported boundary for interaction. Providers define it; developers build callers and implementations. Breaking API changes can disrupt callers unless versioned or migrated.

### 52. Why can't two applications simply access each other's variables?

Separate processes are isolated for safety and reliability. A variable belongs to one program's address space and runtime. Programs communicate through explicit mechanisms such as APIs, files, pipes, or sockets. Shared memory is possible only when deliberately configured on a compatible host. A network API is useful when applications run on separate machines. Each program's OS and runtime manage its own memory. Uncontrolled shared access risks corruption, privacy leaks, and tight coupling.
