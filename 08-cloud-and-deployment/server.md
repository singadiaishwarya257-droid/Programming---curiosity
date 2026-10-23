# Servers

A server is a computer or program that provides a service to other programs, called clients. A web server, for example, can receive HTTP requests and send back pages or data.

“Server” can refer to the physical or virtual machine, or to the software process handling requests. One machine may run many server programs, and one service may use many machines.

## A basic web request

1. A browser resolves a domain using [DNS](../04-internet/dns.md).
2. It connects to a server address and sends an [HTTP](../04-internet/http.md) request, commonly protected by [HTTPS](../04-internet/https.md).
3. The server application handles the request, perhaps querying a database or another API.
4. It returns a response for the browser to display.

Servers need to be configured, monitored, updated, and protected. A server can be hosted in a data center, on a developer's machine, or through a [cloud provider](cloud.md). As demand grows, teams may need to [scale](scaling.md).

## Curiosity questions

91. Where does your application actually run after deployment?
95. What is a server?
98. What happens when a server crashes?
100. If you had to build WhatsApp from scratch, what would you need?

## Explanations guided by the seven questions

### 91. Where does your application actually run after deployment?

Deployment makes the application available to users beyond the developer's machine. It runs as processes or managed workloads on computing infrastructure. Build artifacts are installed or deployed, configured, and started. On servers, containers, edge platforms, mobile devices, or a mix. It runs after a deployment pipeline or operator starts it. Developers, platform teams, and cloud or hosting providers operate the pieces. Incorrect configuration or unavailable infrastructure can prevent startup.

### 95. What is a server?

Clients need a system that provides data or operations. A server is a program, machine, or role that serves requests. It listens for requests, processes them, and sends responses. It can run locally, in a data center, or in the cloud. It operates while its service is available. Server software handles requests; operators maintain the infrastructure. Failure may interrupt service unless redundancy or recovery is configured.

### 98. What happens when a server crashes?

The service stops handling work until it recovers or is replaced. Its process or machine becomes unavailable or unhealthy. Health checks detect failure; a supervisor may restart or route elsewhere. The outage affects the failed instance and any dependent components. Detection and recovery take time, depending on monitoring and architecture. Operators, orchestrators, load balancers, and clients respond. Redundancy can maintain service, but lost in-memory state may need recovery.

### 100. If you had to build WhatsApp from scratch, what would you need?

People need reliable private communication across devices and networks. The system needs clients, identity, messaging, storage, delivery, and operations. APIs accept messages; queues and services route them; clients synchronize state. Clients run on devices; backend services and durable storage run on infrastructure. Begin with a small secure prototype, then scale from measured needs. Product, client, backend, security, reliability, and operations teams contribute. Network outages, abuse, key loss, and service failures require recovery and safety plans.
