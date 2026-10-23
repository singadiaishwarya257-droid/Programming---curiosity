# IP addresses

An Internet Protocol (IP) address identifies a network interface or endpoint so data can be routed across networks. IPv4 addresses are commonly written as four numbers, such as `192.0.2.10`; IPv6 addresses use a longer hexadecimal format, such as `2001:db8::10`.

## Addressing and routing

When a device sends data, network equipment uses destination addresses to forward packets toward the correct network. IP provides addressing and delivery across networks, but it does not guarantee that every packet arrives, arrives only once, or arrives in order. Higher-level protocols handle additional behavior where needed.

Some addresses are public and reachable across the internet; others are private and used within local networks. A network address translation (NAT) device may allow multiple local devices to share a public IPv4 address.

Domain names are easier for people to remember, so [DNS](dns.md) can resolve names to IP addresses. Browsers then use protocols such as [HTTP](http.md), often protected by [HTTPS](https.md), to exchange application data.

## Curiosity questions

44. What is an IP address?
45. Why do we need ports?
49. How does your request travel thousands of kilometres?

## Explanations guided by the seven questions

### 44. What is an IP address?

Networks need destination information to route packets. An IP address identifies a network interface or endpoint for routing. Routers forward packets using address prefixes and routing tables. It is assigned to an interface or network endpoint, not necessarily a person. It is used when sending IP packets. Network administrators, providers, and address-management systems assign addresses. Addresses can change, be shared through NAT, or be unreachable.

### 45. Why do we need ports?

One host can run many network services at once. A port number helps deliver transport traffic to an application endpoint. TCP or UDP uses port numbers alongside IP addresses. Ports are part of transport-layer communication on a device. A client connects to a particular service, such as HTTPS on port 443. Applications listen on ports; the OS routes traffic to them. A blocked or incorrect port can prevent the connection.

### 49. How does your request travel thousands of kilometres?

A client and server may be on distant networks. Data is split into packets that routers forward across interconnected networks. Routing tables choose next hops; transport protocols manage delivery behavior. Packets traverse local networks, providers, exchange points, and destination networks. During active network communication, often over many intermediate links. Routers and network operators forward traffic. Congestion or link failure can delay, reroute, or drop packets.

### Rabbit hole: If the Internet disappeared tomorrow, which parts of an application would still work?

Understanding dependencies reveals what requires remote connectivity. Local code and cached data may work; remote APIs and services may not. An offline mode uses local storage and queues changes for later synchronization. The surviving functionality runs on the user's device or local network. It works while required local resources remain available. Application designers decide which features support offline use. Unsynced changes can conflict when connectivity returns.
