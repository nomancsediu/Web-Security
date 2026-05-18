# Cryptographic Failures

Previously known as 'Sensitive Data Exposure', cryptographic failures occur when applications fail to properly protect data through encryption.

## Common Issues

- Transmitting data in cleartext (HTTP instead of HTTPS)
- Using weak or deprecated algorithms
- Improper key management
- Storing passwords without proper hashing
- Not enforcing encryption (e.g., missing HSTS)

## Prevention

- Classify data and apply appropriate encryption
- Use strong, up-to-date algorithms
- Encrypt data in transit (TLS 1.2+) and at rest
- Use proper key management
- Hash passwords with bcrypt/Argon2
