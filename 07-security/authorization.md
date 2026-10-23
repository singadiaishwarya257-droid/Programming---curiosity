# Authorization

Authorization answers: **“What are you allowed to do?”** It decides which actions an authenticated user, service, or anonymous visitor may perform.

For example, an application might allow any visitor to read public articles, signed-in members to comment, and editors to publish. Authorization rules should be checked on the server for every protected operation; hiding a button in the interface is not a security control.

## Common approaches

- **Role-based access control (RBAC):** permissions are associated with roles such as reader or editor.
- **Attribute-based access control (ABAC):** decisions use properties of the user, resource, and context.
- **Access control lists (ACLs):** a resource lists which identities may perform which actions.

Apply the principle of least privilege: give each identity only the permissions it needs. Check access at the point of use and consider ownership, tenant boundaries, and changes in permissions.

Authentication establishes identity; authorization makes a permission decision. Both should be part of the design of APIs and applications. See [authentication](authentication.md).

## Curiosity questions

76. What happens if someone changes an API request?
78. How does a server know whether you are authorized?
80. How can one careless line of code expose millions of users?

### Related security question

77. What is CORS? CORS is a browser security policy that controls certain cross-origin requests; it is not a replacement for server-side authorization.

## Explanations guided by the seven questions

### 76. What happens if someone changes an API request?

Clients are under user control, so servers cannot trust submitted data. The server receives modified parameters, body, headers, or resource identifiers. Server-side validation and authorization determine whether to accept the request. Checks belong at the API boundary and relevant business-logic operations. Every request must be validated, including requests from the official UI. The server enforces policy; security testers can verify it. Missing checks can enable unauthorized data access or changes.

### 78. How does a server know whether you are authorized?

Authentication alone does not grant access to every resource. Authorization is a policy decision about an identity, action, and resource. The server checks roles, permissions, ownership, attributes, or policy rules. Checks occur on the server before protected data or operations are exposed. At each protected action, not only when a page first loads. The application enforces rules defined by its owners and administrators. A missed object-level check can expose another user's records.

### 80. How can one careless line of code expose millions of users?

A shared service can apply one mistake to many accounts at scale. A missing authorization check, unsafe query, or public storage rule can expose bulk data. Attackers or accidental callers reach a vulnerable path and retrieve or alter records. The flaw may be in an API, database query, configuration, or logging path. Exposure begins when the vulnerable code is deployed and reachable. Developers, reviewers, operators, and security teams share prevention and response work. Revoke access, contain exposure, preserve evidence, notify affected parties as required, and fix the root cause.

### 77. What is CORS?

Browsers need a controlled way to permit cross-origin page scripts to read responses. CORS is a browser-enforced policy using server response headers. The browser checks whether the response permits the requesting origin and method. It applies to browser cross-origin requests; it is not general server authorization. It matters when a page's origin differs from an API's origin. API servers set policy headers; browsers enforce them for scripts. A permissive policy can expose responses to untrusted sites, but does not alone bypass authentication.
