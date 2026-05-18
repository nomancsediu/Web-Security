# Permissions Policy

The Permissions Policy header (formerly Feature-Policy) controls which browser features and APIs can be used in the page and its iframes.

## Common Permissions

```
Permissions-Policy: camera=(), microphone=(), geolocation=(self "https://trusted.example.com"), payment=(self)
```

This example disables camera and microphone, allows geolocation only from the same origin and a trusted domain, and allows payments only from the same origin.
