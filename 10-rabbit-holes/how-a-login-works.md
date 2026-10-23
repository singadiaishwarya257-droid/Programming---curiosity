# How does a login work?

A login is a sequence of checks that lets a service authenticate a user and establish a session. The implementation differs, but a password-based flow might look like this:

1. You send an account identifier and password to the service over HTTPS.
2. The server finds the account and verifies the submitted password against a stored password hash.
3. If the credentials are valid and any required extra checks pass, the server creates a session.
4. The server gives the browser a session cookie or another credential.
5. Later requests present that credential so the server can recognize the session.
6. The server checks [authorization](../07-security/authorization.md) before allowing protected actions.

The password should not be stored in plain text. Services use a password-specific hashing scheme and unique salt. Session credentials should be protected, scoped, and expired or revoked appropriately. HTTPS protects credentials while they travel, but the application must also defend against phishing, credential guessing, stolen sessions, and insecure recovery flows.

Authentication establishes identity; authorization determines permissions. Read [authentication](../07-security/authentication.md), [hashing](../07-security/hashing.md), and [encryption](../07-security/encryption.md) for the concepts behind the flow.

## Curiosity question

When you click Login, how does your password travel from your phone to the server and come back as “Login successful”?

## Explanations guided by the seven questions

### Rabbit hole: How does a login request travel and return success?

The service must verify identity before granting a session. Credentials travel to an authentication endpoint; a success response establishes a session. HTTPS protects transport; the server verifies a password hash and issues a session credential. From the device through networks to the service, then back to the client. The flow begins on submission and ends with success, rejection, or timeout. User, client, network, authentication service, credential store, and session system participate. Invalid credentials are rejected; stolen sessions need expiry, revocation, and protection.
