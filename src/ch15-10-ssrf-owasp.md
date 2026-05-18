# Server-Side Request Forgery

SSRF occurs when a web application fetches a remote resource without validating the user-supplied URL. It allows an attacker to coerce the application to send a crafted request to an unexpected destination.

## Impact

- Access to internal services and metadata APIs
- Internal port scanning
- Remote code execution in some cases
- Data exfiltration

## Prevention

- Validate and sanitize all user-supplied URLs
- Use allowlists for permitted domains
- Block requests to private/reserved IP ranges
- Disable unnecessary URL schemes
- Implement network segmentation
