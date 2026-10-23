# JavaScript

JavaScript is a programming language widely used to make web pages interactive. It also runs on servers and in other environments through JavaScript runtimes.

```javascript
const names = ["Ada", "Grace"];
for (const name of names) {
  console.log(`Hello, ${name}!`);
}
```

JavaScript is dynamically typed and supports asynchronous programming, which is important for handling work such as network requests without blocking an entire application. In browsers, JavaScript can interact with page content through browser APIs. On servers, runtimes such as Node.js provide APIs for files, networking, and other tasks.

JavaScript and Java are separate languages despite their similar names. TypeScript is a related language that adds a static type system and is commonly compiled to JavaScript. The best choice depends on the target environment, team, and libraries. Compare [Python](python.md), [Java](java.md), and [all three](python-vs-javascript-vs-java.md).

## Curiosity questions

82. Why is JavaScript used in browsers?
83. Why is Node.js able to run JavaScript on servers?

## Explanations guided by the seven questions

### 82. Why is JavaScript used in browsers?

Web pages need programmable behavior and interaction in the browser. JavaScript is a language with broad browser support and web APIs. A browser runtime executes scripts and exposes controlled page and network APIs. It runs in browser engines on many user devices. It executes in response to page loading and user or network events. Browser vendors implement runtimes; web developers write scripts. Poorly written scripts can slow pages, so browsers isolate and limit capabilities.

### 83. Why is Node.js able to run JavaScript on servers?

Server applications need a runtime and APIs beyond the browser. Node.js combines a JavaScript engine with server-side libraries. The engine executes JavaScript; Node APIs provide networking, files, and event-driven I/O. It runs as a process on servers or developer machines. Use it for backend services when its runtime and ecosystem fit. The Node.js project maintains the runtime; developers build services. CPU-heavy blocking work can delay other tasks on an event loop.
