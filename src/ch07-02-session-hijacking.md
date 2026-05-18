# Session Hijacking

Session hijacking occurs when an attacker steals a valid session ID and uses it to impersonate the legitimate user. This can be achieved through various means:

- **Network sniffing** - Intercepting unencrypted session cookies on the network
- **XSS attacks** - Stealing cookies via JavaScript (if HttpOnly is not set)
- **Predictable session IDs** - Guessing session IDs if they are not sufficiently random
- **Session fixation** - Forcing a user to use a known session ID

## Prevention

- Always use HTTPS with Secure cookies
- Set the HttpOnly flag on session cookies
- Use strong, random session ID generators
- Regenerate session IDs after authentication
- Implement IP binding or user-agent checking as additional verification
