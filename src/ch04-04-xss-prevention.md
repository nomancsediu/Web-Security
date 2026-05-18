# XSS Prevention and Mitigation

Preventing XSS requires a multi-layered approach that addresses both input handling and output encoding.

## Output Encoding

Context-sensitive output encoding is the most important defense:

- **HTML body**: Encode special characters
- **HTML attributes**: Encode all special characters
- **JavaScript**: Use JavaScript encoding for data in script blocks
- **URL**: Encode data in URL parameters
- **CSS**: Encode data in style blocks

## Content Security Policy (CSP)

CSP restricts which scripts can execute on a page:

```
Content-Security-Policy: default-src 'self'; script-src 'self'
```

## Framework Protections

Modern frameworks provide built-in XSS protections:

- React automatically escapes JSX expressions
- Angular sanitizes values bound to the DOM
- Vue.js escapes HTML interpolation
- Django templates auto-escape by default
