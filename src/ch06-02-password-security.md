# Password Security

Passwords remain the most common form of authentication, making password security a critical concern.

## Password Storage

Never store passwords in plaintext. Use adaptive hashing algorithms:

- **bcrypt** - Designed for password hashing with built-in salt
- **scrypt** - Memory-hard function resistant to GPU attacks
- **Argon2** - Winner of the Password Hashing Competition

## Password Policies

- Minimum length of 12+ characters
- Check against commonly used passwords
- Implement rate limiting on login attempts
- Use haveibeenpwned API to check for breached passwords
