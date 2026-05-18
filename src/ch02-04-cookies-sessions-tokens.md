# Cookies, Sessions, and Tokens

The web was designed to be stateless. That means every request is independent and the server does not remember you from one request to the next. But modern web applications need to remember things. They need to know you are logged in. They need to remember what is in your shopping cart. They need to know your preferences.

That is where cookies, sessions, and tokens come in. They are the mechanisms that add state to the stateless web. And because they are so central to how applications work, they are also a major target for attackers.

## Cookies

Cookies are small pieces of data that the server sends to your browser, and your browser sends back with every request to that domain. They were invented in 1994 to solve the "how do I remember this user" problem, and they are still the primary mechanism for maintaining state.

### How Cookies Work

1. You visit a website and log in
2. The server creates a session and sends a `Set-Cookie` header in the response
3. Your browser stores the cookie
4. Every future request to that domain includes the cookie in a `Cookie` header
5. The server reads the cookie and knows who you are

### Cookie Attributes That Matter

A cookie is not just a name and value. It has important security attributes:

**Secure.** When set, the cookie is only sent over HTTPS connections. This prevents someone on the same network from stealing it. Always use this for sensitive cookies.

**HttpOnly.** When set, JavaScript cannot access the cookie. This protects against XSS attacks that try to steal cookies with `document.cookie`. Always use this for session cookies.

**SameSite.** Controls when the cookie is sent with cross site requests. There are three values:
- **Strict:** Never sent with cross site requests. Strongest protection but can break user experience, like following a link to your site from an email.
- **Lax:** Sent with top level navigation but not with cross site POST requests or iframe loads. This is the default in modern browsers and is a good balance.
- **None:** Always sent with cross site requests. Requires the Secure flag. Use this only if you really need cross site cookies.

**Domain.** Controls which domains receive the cookie. Be careful here. Setting it too broadly can expose the cookie to subdomains it should not reach.

**Path.** Controls which URL paths receive the cookie.

**Expires / Max-Age.** How long the cookie lasts. Session cookies without an expiry date are deleted when the browser closes. Persistent cookies stick around until they expire.

### Best Practices for Cookies

```
Set-Cookie: session=abc123; Secure; HttpOnly; SameSite=Lax; Path=/
```

This is what a well configured session cookie looks like. Use this as your baseline.

## Sessions

Sessions are server side storage for user data. The idea is simple: instead of storing everything in the cookie, you store just a session ID in the cookie and keep all the actual data on the server.

### How Sessions Work

1. You log in
2. The server creates a session object in its storage (memory, database, Redis, etc.)
3. The server sends you a cookie with the session ID
4. On future requests, the server looks up the session data using that ID

### Security Concerns with Sessions

**Session hijacking.** If someone steals your session ID, they can impersonate you. This can happen through network sniffing, XSS, or predictable session IDs.

**Session fixation.** An attacker forces you to use a session ID they already know. After you log in, they use that same ID to access your account.

**Session prediction.** If session IDs are not random enough, an attacker might be able to guess valid ones.

### Session Best Practices

- Use **cryptographically random** session IDs (128 bits minimum)
- **Regenerate the session ID** after login to prevent fixation
- Set a **session timeout** so inactive sessions expire
- Store session data **server side**, never trust client side data
- **Invalidate sessions** on the server when users log out, not just on the client

## Tokens (JWT)

JSON Web Tokens, or JWTs, are a different approach. Instead of storing session data on the server, everything is stored in the token itself. The server does not need to look anything up. It just verifies the token signature and trusts the data inside.

### JWT Structure

A JWT has three parts separated by dots:

```
header.payload.signature
```

The **header** says what algorithm was used. The **payload** contains the actual data (called claims). The **signature** proves the token has not been tampered with.

Here is what a decoded JWT looks like:

```json
// Header
{
  "alg": "HS256",
  "typ": "JWT"
}

// Payload
{
  "sub": "1234567890",
  "name": "Noman",
  "iat": 1516239022,
  "exp": 1516242622
}
```

### Where JWTs Go Wrong

JWTs are powerful but they have some common pitfalls:

**The "none" algorithm attack.** If the server accepts tokens with the algorithm set to "none", anyone can create a valid token with any claims they want. Always validate the algorithm.

**Algorithm confusion.** Some implementations accept either HMAC or RSA algorithms. An attacker who knows the public key can sign a token using HMAC with the public key as the secret. The server might verify it incorrectly.

**Weak secrets.** If you use HMAC and your secret is weak or common, an attacker can brute force it and sign their own tokens.

**No revocation.** JWTs are stateless. Once issued, they are valid until they expire. There is no easy way to revoke a JWT. If a token is stolen, the attacker can use it until it expires.

**Storing sensitive data.** The payload is just base64 encoded, not encrypted. Anyone who gets the token can read the data. Never put passwords or secrets in a JWT payload.

### JWT Best Practices

- Use **strong secrets** (32+ characters, random) or better yet, use **asymmetric algorithms** like RS256 or ES256
- Set **short expiration times** (15 minutes for access tokens)
- Use **refresh tokens** for longer sessions
- **Never store sensitive data** in the payload
- Store tokens in **HttpOnly cookies**, not localStorage, to protect against XSS
- Implement a **token blacklist** if you need revocation

## Cookies vs Sessions vs Tokens: When to Use What

There is no single right answer. Here is a simple way to think about it:

- **Cookies + Server Sessions** are great for traditional web applications. The server controls everything and can easily invalidate sessions.

- **JWTs** are great for APIs and microservices where you want stateless authentication. But you need to handle expiration and revocation carefully.

- **Cookies with JWTs inside** can give you the best of both worlds. The cookie is HttpOnly (safe from XSS) and the JWT inside means the server can verify without a database lookup.

## Key Takeaways

- Cookies, sessions, and tokens are how the web remembers who you are.
- Always set Secure, HttpOnly, and SameSite flags on cookies.
- Sessions store data server side. Tokens store data client side.
- JWTs are not encrypted. Never put secrets in the payload.
- Store tokens in HttpOnly cookies, not localStorage.
- There is no perfect solution. Choose based on your application's needs.

Now that we understand the fundamentals, we are ready to dive into actual attacks. Next up: injection attacks, one of the most common and dangerous classes of web vulnerabilities.
