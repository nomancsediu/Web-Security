# Cookies, Sessions, and Tokens

Cookies, sessions, and tokens are the mechanisms that web applications use to maintain state across the inherently stateless HTTP protocol. Understanding how these mechanisms work—and their security implications—is fundamental to web security.

## Cookies

Cookies are small pieces of data stored by the browser and sent with every subsequent request to the same domain. They were originally designed for maintaining state but have evolved to serve many purposes.

### Cookie Attributes

- **Expires/Max-Age** - How long the cookie persists
- **Domain** - Which domains receive the cookie
- **Path** - Which paths on the domain receive the cookie
- **Secure** - Only sent over HTTPS
- **HttpOnly** - Not accessible via JavaScript
- **SameSite** - Controls when cookies are sent with cross-site requests (Strict, Lax, None)

### Security Best Practices for Cookies

- Always use the `Secure` flag for sensitive cookies
- Always use the `HttpOnly` flag for session cookies
- Use `SameSite=Lax` or `SameSite=Strict` to prevent CSRF
- Set appropriate `Domain` and `Path` to minimize cookie scope
- Use short expiration times for session cookies
- Regenerate session IDs after login

## Sessions

Sessions are server-side data structures that track user state. A session ID (typically stored in a cookie) links the user to their session data on the server.

### Session Security Concerns

- **Session hijacking** - Stealing a session ID to impersonate a user
- **Session fixation** - Forcing a user to use a known session ID
- **Session prediction** - Guessing valid session IDs

## Tokens (JWT)

JSON Web Tokens (JWT) are a stateless alternative to server-side sessions. They encode user claims in a signed (and optionally encrypted) token that the client stores and sends with each request.

### JWT Structure

A JWT consists of three parts separated by dots:
1. **Header** - Algorithm and token type
2. **Payload** - Claims (user data, expiration, etc.)
3. **Signature** - Ensures the token has not been tampered with

### Token Security Considerations

- Never store sensitive data in JWT payloads (they are base64-encoded, not encrypted)
- Use strong signing algorithms (RS256, ES256)
- Set short expiration times
- Implement proper token revocation mechanisms
- Store tokens securely on the client side (prefer HttpOnly cookies over localStorage)
