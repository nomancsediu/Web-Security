# JSON Web Tokens (JWT)

JSON Web Tokens are a compact, URL-safe way to represent claims between two parties, widely used for authentication.

## Security Considerations

- **Algorithm confusion** - Attackers may change the algorithm to 'none'
- **Weak secrets** - JWTs signed with weak secrets can be cracked
- **Token theft** - Stolen tokens can be used until expiration
- **No built-in revocation** - JWTs are stateless and cannot be easily revoked

## Best Practices

- Use strong, unique signing keys
- Prefer asymmetric algorithms (RS256, ES256)
- Set short expiration times
- Implement token rotation and refresh tokens
