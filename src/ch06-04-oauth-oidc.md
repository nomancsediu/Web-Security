# OAuth 2.0 and OpenID Connect

OAuth 2.0 is an authorization framework that allows third-party applications to obtain limited access to user accounts. OpenID Connect (OIDC) adds an identity layer on top of OAuth 2.0.

## OAuth 2.0 Flows

- **Authorization Code Flow** - Most secure, recommended for server-side apps
- **Authorization Code Flow with PKCE** - For public clients (SPAs, mobile)
- **Client Credentials Flow** - For server-to-server communication

## Common OAuth Vulnerabilities

- Redirect URI validation bypass
- CSRF during authorization flow
- Token leakage via referrer headers
- Weak client secrets
