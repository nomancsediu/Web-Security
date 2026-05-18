# Hashing and Salting

Hashing is a one-way function that converts data into a fixed-size digest. It is fundamental to password storage, data integrity verification, and digital signatures.

## Cryptographic Hash Functions

- **SHA-256/SHA-3** - Standard hash functions
- **bcrypt/scrypt/Argon2** - Password hashing algorithms (include salt and work factor)

## Why Salt?

Salting adds random data before hashing, preventing rainbow table attacks and ensuring that identical passwords produce different hashes.

## Password Hashing Best Practices

- Use bcrypt, scrypt, or Argon2 (not SHA-256 directly)
- Use a unique salt per password
- Use an appropriate work factor/cost parameter
- Never use MD5 or SHA-1 for passwords
