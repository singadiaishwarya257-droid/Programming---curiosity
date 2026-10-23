# HTTP

Hypertext Transfer Protocol (HTTP) is a protocol clients and servers use to exchange web resources and data. A browser might send a request for a page, and a server might respond with HTML, JSON, an image, or an error.

## Request and response

An HTTP request has a method, a target, headers, and sometimes a body. A response has a status code, headers, and often a body.

```http
GET /articles HTTP/1.1
Host: example.com
Accept: application/json
```

Common methods include `GET` to retrieve data, `POST` to submit data, `PUT` or `PATCH` to update data, and `DELETE` to remove data. Status codes offer a broad result: `200` means success, `404` means not found, and `500` indicates a server error.

HTTP is stateless in the sense that each request is understood independently by the protocol; applications can add continuity using cookies, tokens, or other state. Plain HTTP does not encrypt traffic, so websites commonly use [HTTPS](https.md). See [request and response](../05-apis/request-response.md) for the API perspective.

## Curiosity questions

46. What is HTTP?
48. What happens when you click a button on a website?
50. How does the server know where to send the response?

## Explanations guided by the seven questions

### 46. What is HTTP?

Clients and servers need shared rules for exchanging web resources. HTTP is an application protocol for requests and responses. Methods, URLs, headers, status codes, and optional bodies describe exchanges. It operates between clients and servers, usually over TCP or QUIC. Browsers and APIs use it to fetch or submit resources. Clients send requests; servers return responses. Plain HTTP exposes traffic to observation or tampering on untrusted networks.

### 48. What happens when you click a button on a website?

The button may submit input or trigger an application action. Browser code handles the event and may update the page or send a request. Event handlers run JavaScript, validate data, and call browser or network APIs. The initial event occurs in the browser; server work may occur remotely. The configured action runs after the click event is delivered. Browser, page code, and possibly an API server participate. Validation, network, or server errors should be shown and handled.

### 50. How does the server know where to send the response?

The response must return to the client that made the request. The connection associates the response with a client endpoint. Transport connection state and packet addresses route data back. The server's network stack sends through routers toward the client's address. The server writes the response on the request's connection. The server OS, network, and client OS handle delivery. A broken connection can prevent delivery even if the server finished work.
