# HSTS and Certificate Pinning

HTTP Strict Transport Security (HSTS) forces browsers to only use HTTPS connections to your site, preventing protocol downgrade and cookie hijacking attacks.

## HSTS Configuration

```
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
```

## HSTS Preload

Submitting your domain to the HSTS preload list ensures browsers will only connect via HTTPS even on the first visit.

## Certificate Pinning

Certificate pinning associates a specific certificate or public key with a server, preventing man-in-the-middle attacks even with a compromised CA. While HTTP pinning (HPKP) has been deprecated, pinning can still be implemented in native mobile applications.
