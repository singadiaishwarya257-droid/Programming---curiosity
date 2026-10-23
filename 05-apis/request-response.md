# Request and response

Many web APIs follow a request-response pattern. A client sends a request to a server; the server processes it and returns a response. The exchange often uses HTTP.

## A request contains

- A destination, such as a URL
- A method describing the operation
- Headers with metadata, such as content type or authorization
- An optional body containing data

## A response contains

- A status code indicating the broad outcome
- Headers describing the response
- An optional body with data or an error explanation

For example, a client could send `GET /books/42` and receive status `200` with a JSON body such as `{"id": 42, "title": "A Sample Book"}`. If that book does not exist, the server might return `404`. Exact choices depend on the API's contract.

Clients should handle expected error responses, timeouts, and malformed data rather than assuming every request succeeds. Sensitive credentials should not be placed in public URLs. APIs commonly use HTTPS to protect requests in transit; see [HTTP](../04-internet/http.md), [HTTPS](../04-internet/https.md), and [REST APIs](rest-api.md).

## Curiosity questions

53. What happens when a React application calls a Node.js or Python API?
54. What is a request?
55. What is a response?
56. Why do APIs commonly use JSON?
59. What happens if an API takes 10 seconds to respond?
60. What happens if the API server is completely down?
90. Can different programming languages communicate with each other?

### Rabbit hole

If Python, JavaScript, and Java are completely different languages, how can they communicate with each other?

### Rabbit hole: How can different programming languages communicate?

Different languages let components use tools suited to their strengths, then cooperate through an agreed interface. They can exchange data with protocols such as HTTP and JSON, queues, RPC, or native bindings, whether within one process, on a machine, or across a network. This is useful when components are developed or deployed independently, but mismatched schemas, versions, or encodings can break communication.

## Explanations guided by the seven questions

### 53. What happens when a React application calls a Node.js or Python API?

The front end needs data or an operation provided by a backend. The browser sends a network request; the server returns a response. Client code serializes input, sends HTTP, and parses the returned payload. React code runs in the browser; Node.js or Python usually runs on a server. The call may happen after page load or a user action. Browser, network, API server, and possibly database services participate. Timeouts, errors, invalid data, or server outages must be handled.

### 54. What is a request?

A client needs to describe the operation and data it wants. A request is a message sent to a service. It includes a destination, method, headers, and sometimes a body. It travels over a network to the server endpoint. It is sent when the application needs a resource or action. A client constructs it; a server receives it. Invalid or unauthorized requests should receive a suitable error response.

### 55. What is a response?

The client needs the result of its request. A response reports an outcome and may contain returned data. The server sends a status code, headers, and optional body. It travels back over the connection to the client. It follows processing or failure of a request. The server produces it; the client interprets it. The client should handle failure statuses, missing data, and malformed responses.

### 56. Why do APIs commonly use JSON?

A simple interoperable format makes structured data easy to exchange. JSON is a text format for objects, arrays, strings, numbers, booleans, and null. Each side serializes and parses JSON using standard libraries. It is sent in request and response bodies. It is useful for web data with common structures. APIs and clients across many languages support it. Large or specialized data may suit binary formats better; schemas still need validation.

### 59. What happens if an API takes 10 seconds to respond?

Waiting affects user experience and consumes client or server resources. The client remains pending unless it times out or cancels the request. Timeouts, loading states, retries, caching, or asynchronous jobs can help. Delay may be in the network, server, database, or downstream dependency. The client should use a deadline appropriate to the operation. Client and server teams monitor latency and identify bottlenecks. Blind retries can multiply load; retry safely with limits and backoff.

### 60. What happens if the API server is completely down?

The client cannot obtain the service's normal response. Connections fail or time out until service is restored. Redundant instances, health checks, and graceful error handling improve resilience. Failure may affect one instance, region, or the whole service. Clients detect it through connection errors, health checks, or deadlines. Operators investigate; clients should show a useful failure state. Cached or offline functionality may continue, but stale data must be handled.

### 90. Can different programming languages communicate with each other?

Components can use the language best suited to each part of a system. They exchange data through shared protocols or foreign-function interfaces. Common methods include HTTP/JSON, queues, files, RPC, and native bindings. Communication can happen within one process or across a network. Use an interoperability boundary when separate components need to cooperate. Each component's runtime and interface implementation participate. Mismatched schemas, encodings, or versions break communication.
