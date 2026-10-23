# Encryption

Encryption transforms readable information (plaintext) into an unreadable form (ciphertext) using an algorithm and a key. Decryption uses the appropriate key to recover the information.

## Two broad approaches

- **Symmetric encryption:** the same secret key, or closely related keys, encrypts and decrypts. It is efficient for protecting large amounts of data.
- **Asymmetric cryptography:** a public/private key pair supports operations such as establishing shared keys or creating digital signatures. The private key must be protected.

Secure systems often combine these approaches. For example, [HTTPS](../04-internet/https.md) uses public-key cryptography during setup and symmetric encryption for most data in the established connection.

The algorithm alone is not enough: key generation, storage, rotation, and use matter. Do not invent your own cryptographic algorithm or reuse keys carelessly; use well-reviewed libraries and protocols. Encryption protects confidentiality, but it does not automatically establish that a message is authentic or that an application is safe. See [hashing](hashing.md) for a distinct one-way operation.

## Curiosity questions

74. What is encryption?

## Explanations guided by the seven questions

### 74. What is encryption?

It protects information from parties without the required key. Encryption transforms plaintext into ciphertext using a key. A cryptographic algorithm encrypts; an authorized key decrypts. It protects data in transit or at rest. Use established protocols and libraries when confidentiality is required. Data owners manage keys; cryptographic software performs transformations. Lost keys can make data unrecoverable; stolen keys can defeat protection.
