# Common Ports and Services

Reference table of commonly encountered ports and their associated services, important for network security assessments.

| Port | Service | Security Notes |
|------|---------|----------------|
| 20/21 | FTP | Unencrypted, avoid |
| 22 | SSH | Secure if configured properly |
| 23 | Telnet | Unencrypted, never use |
| 25 | SMTP | Often misconfigured |
| 53 | DNS | Vulnerable to amplification attacks |
| 80 | HTTP | Redirect to HTTPS |
| 443 | HTTPS | Preferred |
| 3306 | MySQL | Should not be exposed |
| 5432 | PostgreSQL | Should not be exposed |
| 8080 | HTTP Proxy | Often exposed accidentally |
