# Broken Access Control

Broken access control is the #1 risk in the OWASP Top 10 (2021). It occurs when users can act outside their intended permissions.

## Common Issues

- IDOR (Insecure Direct Object Reference)
- Privilege escalation (vertical and horizontal)
- Missing access controls on API endpoints
- Forced browsing to unauthorized pages
- JWT manipulation

## Prevention

- Deny by default
- Implement access control mechanisms once, reuse throughout the application
- Enforce record ownership rather than just accepting user-provided IDs
- Disable directory listing
- Log and alert on access control failures
