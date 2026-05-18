# SameSite Cookie Attribute

The SameSite cookie attribute provides built-in CSRF protection at the browser level.

## SameSite Values

- **Strict**: Cookies only sent with same-site requests
- **Lax**: Cookies sent with same-site requests and top-level navigations (default in modern browsers)
- **None**: Cookies sent with all requests (requires Secure flag)

## Implementation

```
Set-Cookie: session=abc123; SameSite=Lax; Secure; HttpOnly
```
