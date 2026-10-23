# Cloud computing

Cloud computing provides computing resources—such as servers, storage, databases, and networking—over a network, often with on-demand provisioning and usage-based billing.

Cloud services are commonly grouped into:

- **Infrastructure as a Service (IaaS):** virtual machines, networks, and storage that you manage substantially yourself.
- **Platform as a Service (PaaS):** a managed environment for deploying applications.
- **Software as a Service (SaaS):** a complete application delivered for people to use.

The boundaries between these categories are not always sharp. Cloud providers can manage parts of the system, but customers still have responsibilities such as configuring access, protecting data, and understanding costs.

“In the cloud” means someone else's infrastructure is involved—not that the system has no physical machines. Cloud platforms can make it easier to provision resources and scale, but they do not automatically make an application secure, reliable, or inexpensive. See [servers](server.md) and [scaling](scaling.md).

## Curiosity questions

96. What is cloud computing?
97. What is AWS or Azure actually providing?

### Rabbit holes

- When you upload a photo to Instagram, where does that photo actually go?
- If the Internet disappeared tomorrow, which parts of your application would still work?

## Explanations guided by the seven questions

### 96. What is cloud computing?

Organizations can provision computing without owning every machine. Cloud computing delivers on-demand infrastructure and managed services over networks. Providers virtualize resources, automate provisioning, and meter usage. Workloads run in provider-operated data centers across regions. Use it when elasticity or managed infrastructure fits the need and budget. Cloud providers operate infrastructure; customers configure and use services. Outages, misconfiguration, or unexpected usage can affect availability and cost.

### 97. What is AWS or Azure actually providing?

Teams need infrastructure and services without building every layer themselves. They provide compute, storage, networking, databases, identity, and many managed services. Customers provision resources through consoles, APIs, or infrastructure-as-code. Services run in geographically distributed data centers. Choose specific services according to workload, reliability, compliance, and cost needs. Provider teams operate the platform; customers remain responsible for their configuration and data. Provider failures or lock-in can be mitigated with recovery plans and portable designs where justified.

### Rabbit hole: When I upload a photo to Instagram, where does that photo actually go?

The service needs to store, process, and deliver the image. The client uploads bytes and associated metadata to service infrastructure. APIs receive the upload; backend systems validate, transform, and store copies or variants. Images may be placed in distributed object storage and cached near viewers. Upload occurs after the client sends the file and the service accepts it. Client, API, processing pipeline, storage, and content delivery systems participate. Upload failures may require retry; privacy settings govern who can retrieve it.
