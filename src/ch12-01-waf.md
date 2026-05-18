# Web Application Firewalls

A WAF sits between the web application and the internet, analyzing HTTP traffic to detect and block malicious requests.

## How WAFs Work

- **Signature-based detection** - Matches known attack patterns
- **Anomaly-based detection** - Identifies deviations from normal traffic
- **Behavioral analysis** - Detects suspicious patterns over time

## Popular WAF Solutions

- Cloudflare WAF
- AWS WAF
- ModSecurity (open source)
- Akamai Kona Site Defender

## Limitations

- WAFs can be bypassed with encoding and obfuscation
- False positives can block legitimate traffic
- Not a substitute for secure coding practices
