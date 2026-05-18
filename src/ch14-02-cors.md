# Cross-Origin Resource Sharing

CORS is a mechanism that allows servers to relax the Same-Origin Policy in a controlled way, permitting specific cross-origin requests while blocking others.

## Simple Requests vs Preflight

Simple requests (GET, POST with certain content types) are sent directly. Non-simple requests trigger a preflight OPTIONS request first.

## CORS Headers

```
Access-Control-Allow-Origin: https://trusted.example.com
Access-Control-Allow-Methods: GET, POST, PUT, DELETE
Access-Control-Allow-Headers: Content-Type, Authorization
Access-Control-Allow-Credentials: true
Access-Control-Max-Age: 86400
```

## Security Considerations

- Never use `Access-Control-Allow-Origin: *` with credentials
- Validate the Origin header against an allowlist
- Be specific about allowed methods and headers
