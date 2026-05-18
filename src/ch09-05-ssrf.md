# Server-Side Request Forgery (SSRF)

SSRF occurs when an attacker can cause a server to make requests to unintended locations. This can be used to access internal services, scan internal networks, and exfiltrate data.

## Attack Scenarios

- Accessing internal APIs (e.g., cloud metadata endpoints)
- Scanning internal network ports
- Reading local files via file:// protocol
- Bypassing firewalls and access controls

## Prevention

- Validate and sanitize all URLs before making server-side requests
- Use allowlists of permitted domains and IP ranges
- Block requests to private IP ranges (10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16)
- Block cloud metadata endpoints (169.254.169.254)
- Implement network segmentation
