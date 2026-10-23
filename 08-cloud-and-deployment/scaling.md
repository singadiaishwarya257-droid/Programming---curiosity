# Scaling

Scaling is changing a system's capacity so it can handle more work or meet performance and reliability goals.

- **Vertical scaling (scale up):** give one machine more resources, such as memory or CPU.
- **Horizontal scaling (scale out):** add more machines or application instances and distribute work among them.

Horizontal scaling can increase capacity and resilience, but it introduces coordination: requests need routing, shared data needs careful design, and instances need to be monitored and updated.

Systems can also scale different components independently. A cache can reduce repeated database reads; a queue can smooth bursts of background work; a database index can improve a measured query. These choices add complexity and should address an observed need.

There is no single scale-up point that fits every application. Measure response time, throughput, errors, and resource use, then identify the bottleneck. Scaling is not a substitute for correctness or good design. See [servers](server.md), [cloud computing](cloud.md), and [indexes](../06-databases/indexes.md).

## Curiosity questions

92. What happens when 1 user uses your application?
93. What changes when 1 million users use it?
94. Why can't we simply buy one huge computer?
99. How do Netflix, YouTube, or Instagram handle millions of users?

### Rabbit hole

How can millions of people use the same application at the same time?

## Explanations guided by the seven questions

### 92. What happens when 1 user uses your application?

A single request exercises the application's full path. A client interacts with application logic and possibly storage or external services. The request is routed, processed, and returned as a response. Work may span device, network, server, and database. Each action triggers the relevant path. User, client software, backend, and dependencies participate. One slow dependency can still make the whole interaction feel slow.

### 93. What changes when 1 million users use it?

More concurrent demand can exceed single-instance capacity. Traffic, state, storage, and failure rates become larger operational concerns. Systems use load balancing, caching, partitioning, queues, and additional instances as measured. Work is distributed across services, regions, and data stores. Scale when measurements show demand or reliability needs require it. Engineering and operations teams monitor and adjust capacity. Bottlenecks move; scaling one component may overload another.

### 94. Why can't we simply buy one huge computer?

A single machine has cost, physical, reliability, and scaling limits. Vertical scaling is increasing resources on one host. Hardware upgrades add capacity until a component or budget becomes a limit. The machine remains one failure and placement boundary. A larger host can be simplest while it meets requirements. Operators select capacity based on workload and budget. The host fails or reaches its maximum; distributed designs may then be needed.

### 99. How do Netflix, YouTube, or Instagram handle millions of users?

Large services need capacity, low latency, and resilience at high demand. They use many specialized services and distributed infrastructure. Load balancing, caching, content delivery, data partitioning, queues, and automation help. Services operate across data centers, regions, and edge networks. Components scale based on traffic patterns and measured bottlenecks. Large engineering and operations teams build and run these systems. Failures are isolated where possible, while monitoring and fallback behavior reduce impact.

### Rabbit hole: How can millions of people use the same application at the same time?

Shared services must process concurrent user actions. Requests are distributed among many application instances and supporting systems. Load balancers spread traffic; data stores and queues manage shared work. Across multiple machines, services, and often regions. Capacity is adjusted as demand grows or fluctuates. Platform automation and operations teams coordinate resources. A hot database or overloaded dependency can become the bottleneck.
