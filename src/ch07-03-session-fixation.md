# Session Fixation

Session fixation is an attack where the attacker forces a user to use a session ID known to the attacker. After the user authenticates, the attacker can use the known session ID to access the user's account.

## Attack Methods

- **URL-based session IDs** - Attacker sends a link with the session ID in the URL
- **Cookie injection** - Attacker sets a cookie via XSS or other means
- **Cross-subdomain cookie** - Attacker exploits cookie scope across subdomains

## Prevention

- Regenerate the session ID after login
- Do not accept session IDs from URLs
- Set proper cookie domain and path attributes
- Use the SameSite cookie attribute
