# Subresource Integrity

Subresource Integrity (SRI) allows browsers to verify that external resources (scripts, stylesheets) have not been tampered with by checking a cryptographic hash.

## Implementation

```html
<script src="https://cdn.example.com/library.js"
        integrity="sha384-oqVuAfXRKap7fdgcCY5uykM6+R9GqQ8K/uxy9rx7HNQlGYl1kPzQho1wx4JwY8wC"
        crossorigin="anonymous"></script>
```

## When to Use SRI

- Always for third-party CDNs
- For any external resource you don't control
- As part of a defense-in-depth strategy
