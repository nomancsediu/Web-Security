# Content Security Policy (CSP)

Content Security Policy is a powerful security mechanism that helps prevent XSS and other injection attacks by specifying which sources of content are allowed to be loaded and executed.

## CSP Directives

```
Content-Security-Policy: default-src 'self'; script-src 'self' https://trusted.cdn.com; style-src 'self' 'unsafe-inline'; img-src 'self' data: https:; connect-src 'self' https://api.example.com
```

## Key Directives

- `default-src` - Fallback for other directives
- `script-src` - Controls JavaScript sources
- `style-src` - Controls CSS sources
- `img-src` - Controls image sources
- `connect-src` - Controls fetch, XHR, WebSocket destinations
- `frame-src` - Controls iframe sources

## Reporting

CSP can report violations:

```
Content-Security-Policy-Report-Only: default-src 'self'; report-uri /csp-reports
```
