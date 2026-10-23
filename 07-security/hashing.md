# Hashing

A cryptographic hash function maps input data of any size to a fixed-length output called a hash or digest. A useful cryptographic hash is designed so that small input changes produce very different outputs and it is impractical to recover the input from the digest.

Hashing is one-way; it is not the same as encryption. Encryption is designed so authorized users can recover the original data using a key.

## Password storage

Passwords should not be stored as plain text or protected with a fast general-purpose hash alone. Password storage should use a purpose-built, deliberately slow password-hashing scheme such as Argon2id, scrypt, bcrypt, or PBKDF2, configured appropriately. A unique random salt is stored with each hash. When a user logs in, the system hashes the submitted password with the saved parameters and compares the result securely.

Hashes are also used for integrity checks and content identification, but a hash by itself does not prove who created the data. A digital signature or keyed message authentication code may be needed for authenticity. See [authentication](authentication.md) and [encryption](encryption.md).

## Curiosity questions

75. What is hashing?

## Explanations guided by the seven questions

### 75. What is hashing?

Hashes help compare data, detect changes, and store password verifiers. A hash function maps input to a fixed-size digest. A cryptographic function deterministically computes the digest from input. Hashes are used in files, databases, protocols, and credential systems. Use a suitable hash for integrity; use password-specific hashing for passwords. Applications and cryptographic libraries compute hashes. A hash is not encryption and does not prove authenticity by itself.
