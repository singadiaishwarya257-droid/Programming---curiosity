# Authentication

Authentication answers: **“Who or what are you?”** A system uses it to verify the identity of a user, device, or service.

Common factors include:

- Something you know, such as a password
- Something you have, such as a hardware security key
- Something you are, such as a biometric characteristic

Using more than one independent factor is called multi-factor authentication (MFA). A username is usually an identifier, not proof of identity.

For password-based login, a service should not store plain-text passwords. It should store a password hash produced by a password-specific hashing function with a unique salt. Login systems also need careful session handling, rate limiting, recovery flows, and protection against phishing.

Authentication is different from [authorization](authorization.md): knowing who a user is does not automatically mean they can access every resource. Learn about [hashing](hashing.md) and [encryption](encryption.md) for related security concepts.

## Curiosity questions

71. How does a website know who you are after login?
72. Where is your password stored?
73. Why shouldn't passwords be stored as plain text?
79. What is a token?

### Rabbit hole

When you click Login, how does your password travel from your phone to the server and come back as “Login successful”? Follow the steps in [how a login works](../10-rabbit-holes/how-a-login-works.md).

## Explanations guided by the seven questions

### 71. How does a website know who you are after login?

It needs to associate later requests with an authenticated identity. The server verifies credentials and establishes a session or token. The client presents a protected session credential on later requests. Identity state is checked by the server; a session cookie is held by the browser. After successful authentication, until expiry, logout, or revocation. Identity service, browser, and application server participate. A stolen session credential may let an attacker impersonate the user.

### 72. Where is your password stored?

The service needs a verifier to check future login attempts. Secure services store a salted password hash, not the original password. A password-hashing algorithm derives a verifier using a unique salt and cost parameters. In a protected credential store or user database. It is created or changed during registration or password reset. The authentication service controls access to the stored verifier. A breach exposes verifiers, so strong hashing and unique passwords still matter.

### 73. Why shouldn't passwords be stored as plain text?

A database breach would immediately reveal reusable credentials. Plain text is the original readable password. Store a salted, slow password hash and verify by hashing a login attempt. The verifier belongs in a restricted credential store; plaintext should not be logged. This applies whenever an application accepts passwords. Developers and operators must protect credential handling. Users often reuse passwords, so exposed plaintext can compromise other accounts too.

### 79. What is a token?

A token can represent authorization or a session without resending a password. It is a credential or data object issued for a defined purpose. The client presents it; the server validates signature, scope, expiry, or stored state. It may be carried in a secure cookie or authorization header. It is used after login or to authorize a specific API operation. An identity or authorization service issues it; clients and servers handle it. A stolen bearer token can be misused until it expires or is revoked.
