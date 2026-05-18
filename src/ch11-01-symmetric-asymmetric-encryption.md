# Symmetric and Asymmetric Encryption

Encryption transforms readable data into an unreadable format, protecting it from unauthorized access. There are two fundamental types of encryption: symmetric and asymmetric.

## Symmetric Encryption

Uses the same key for encryption and decryption. Fast and efficient for large amounts of data.

- **AES** - The gold standard for symmetric encryption
- **ChaCha20** - A modern stream cipher

## Asymmetric Encryption

Uses a pair of keys: a public key for encryption and a private key for decryption. Essential for key exchange and digital signatures.

- **RSA** - Widely used for key exchange and signatures
- **ECC** - More efficient than RSA with equivalent security

## Hybrid Encryption

In practice, web security uses both: asymmetric encryption to exchange a symmetric key, then symmetric encryption for the actual data. This is how TLS works.
