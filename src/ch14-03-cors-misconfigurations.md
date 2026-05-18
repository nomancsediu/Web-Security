# CORS Misconfigurations

CORS misconfigurations are a common security issue that can lead to cross-origin data theft and other attacks.

## Common Misconfigurations

- **Reflecting Origin header** - Setting ACAO to the request Origin without validation
- **Using null origin** - Allowing `null` as a valid origin
- **Subdomain trust** - Allowing all subdomains when only specific ones should be trusted
- **Wildcard with credentials** - Combining `ACAO: *` with `Allow-Credentials: true`

## Testing for CORS Misconfigurations

1. Send a request with a different Origin header
2. Check if the response includes permissive CORS headers
3. Try various Origin values (subdomains, null, etc.)
