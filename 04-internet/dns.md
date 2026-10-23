# DNS

The Domain Name System (DNS) helps people use names such as `example.com` instead of remembering numeric IP addresses. It is a distributed lookup system: a DNS resolver finds records that associate a name with information such as an address.

## A simplified lookup

1. Your device checks whether it already has a usable cached answer.
2. It asks a configured recursive resolver to look up the name.
3. If needed, the resolver follows referrals through the DNS hierarchy.
4. The resolver returns the record, which can be cached for its time-to-live (TTL).

Real lookups may take shortcuts because answers are cached, and organizations can configure DNS in many ways. A name may have multiple records and addresses.

DNS answers the question “where can I find this name?” It does not itself load a website or guarantee that the destination is trustworthy. After DNS resolution, a client uses a network protocol to connect to an address. Read about [IP addresses](ip.md), [HTTP](http.md), and [HTTPS](https.md).

## Curiosity questions

41. What happens when you type `google.com` into a browser?
42. How does your computer find Google's server?
43. What is DNS?

## Explanations guided by the seven questions

### 41. What happens when you type `google.com` into a browser?

The browser needs to turn a human-readable name into a network connection. It resolves the name, connects securely, and requests the page. DNS lookup is followed by IP routing, a TLS handshake, and HTTP exchanges. Work occurs in the browser, device, network, and Google's infrastructure. Some steps may be skipped or shortened by caches and existing connections. Browser, resolver, network equipment, and service servers participate. DNS, network, TLS, or server failure can prevent the page from loading.

### 42. How does your computer find Google's server?

Network packets need a routable destination address. The browser obtains an IP address for the requested domain. A resolver answers using cached or authoritative DNS records. The answer points to network infrastructure serving the domain. Resolution happens before connection unless a valid cached address exists. The device's resolver and DNS hierarchy provide the lookup. A domain may resolve to different addresses by location or time.

### 43. What is DNS?

Names are easier for people to use than numeric network addresses. DNS is a distributed system for looking up records associated with names. Resolvers query caches and DNS servers through a hierarchy. DNS data is distributed across resolvers and authoritative servers. It is used when an application needs records for a domain. Domain owners publish records; resolver operators answer client lookups. Expired or incorrect records can direct clients incorrectly or fail lookup.
