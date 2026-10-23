# HTTPS

HTTPS is HTTP sent over a connection protected by Transport Layer Security (TLS). It helps protect communication between a client and server in three important ways:

- **Confidentiality:** encryption helps prevent others on the network from reading the data.
- **Integrity:** tampering with data in transit can be detected.
- **Authentication:** certificates help the client verify the server's identity for a domain.

During a TLS handshake, the client and server negotiate security settings, validate the server certificate, and establish keys for the protected connection. The details depend on the TLS version and configuration.

HTTPS protects data while it travels between the client and the authenticated server. It does not prove that a site is honest, protect a compromised device, or make an application immune to flaws. Users should still check the domain, and services must protect data after it reaches the server.

HTTPS is the secure form commonly used for [HTTP](http.md). Certificate trust and secure keys rely on cryptographic ideas described in [encryption](../07-security/encryption.md).

## Curiosity questions

47. Why was HTTPS created?

## Explanations guided by the seven questions

### 47. Why was HTTPS created?

Web traffic needed protection against eavesdropping and tampering. HTTPS is HTTP protected by TLS. TLS authenticates the server and negotiates keys for encrypted communication. Protection applies between the client and the TLS endpoint. It is used for websites and APIs whenever data should travel securely. Browsers, servers, certificate authorities, and TLS implementations participate. HTTPS cannot make a dishonest site trustworthy or protect a compromised endpoint.
