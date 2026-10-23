# REST APIs

REST (Representational State Transfer) is an architectural style for networked systems. In everyday use, “REST API” often refers to a web API that exposes resources through URLs and uses HTTP methods to act on them.

For a books API, endpoints might look like:

```text
GET    /books       list books
GET    /books/42    retrieve one book
POST   /books       create a book
PATCH  /books/42    update part of a book
DELETE /books/42    delete a book
```

The HTTP method and response status help communicate the operation and its result. A REST-style API commonly represents resources as JSON, though REST does not require JSON.

REST is not simply “JSON over HTTP.” It has architectural constraints, including a uniform interface and stateless interactions. Many APIs described as REST are REST-inspired rather than strictly conforming, which is fine if their behavior is documented and consistent.

Clients should rely on the API contract, not assumptions about implementation. For the parts of each exchange, see [request and response](request-response.md); for the broader idea of an interface, see [what is an API?](what-is-api.md).

## Curiosity questions

57. What are HTTP methods?
58. Why do we have `GET`, `POST`, `PUT`, `PATCH`, and `DELETE`?

## Explanations guided by the seven questions

### 57. What are HTTP methods?

A request needs to indicate its intended operation. Methods are verbs such as `GET`, `POST`, `PUT`, `PATCH`, and `DELETE`. The client sends a method; the server defines behavior for that endpoint. A method is part of an HTTP request. Choose a method that matches the API's documented semantics. API designers specify behavior; clients and servers implement it. Incorrect assumptions about method safety or repeatability can cause duplicate changes.

### 58. Why do we have `GET`, `POST`, `PUT`, `PATCH`, and `DELETE`?

Standard methods make common operations more predictable. `GET` retrieves; `POST` submits or creates; `PUT` replaces; `PATCH` partially updates; `DELETE` removes. Clients use these verbs and servers map them to resource behavior. They are defined by HTTP and used by APIs. Use the method whose documented meaning fits the operation. API designers choose endpoint semantics; clients invoke them. The same method can have API-specific details, so read the contract.
