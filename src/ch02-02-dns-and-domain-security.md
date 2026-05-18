# DNS and Domain Security

The Domain Name System (DNS) is often called the phonebook of the internet. It translates human-readable domain names into IP addresses. Because DNS is a critical part of web infrastructure, DNS security is essential for overall web security.

## How DNS Works

When you type a URL into your browser, the following DNS resolution process occurs:

1. The browser checks its local cache
2. If not found, it queries the operating system's DNS resolver
3. The resolver checks its cache, then queries the recursive DNS server
4. The recursive server queries the root, TLD, and authoritative name servers
5. The IP address is returned and cached at each level

## DNS Security Threats

### DNS Spoofing (Cache Poisoning)
An attacker corrupts the DNS cache to redirect traffic to a malicious server. This can be used for phishing attacks, malware distribution, or man-in-the-middle attacks.

### DNS Amplification Attacks
Attackers use open DNS resolvers to amplify DDoS attacks by sending small queries that generate large responses directed at the victim's IP address.

### Domain Hijacking
An attacker gains control of a domain's registration, allowing them to redirect all traffic to servers under their control.

### Subdomain Takeover
If a subdomain points to a service (like a cloud provider) that has been deprovisioned, an attacker may be able to claim that subdomain on the service provider.

## DNS Security Defenses

- **DNSSEC** - Adds cryptographic signatures to DNS records, ensuring their authenticity
- **DNS over HTTPS (DoH)** - Encrypts DNS queries to prevent eavesdropping
- **DNS over TLS (DoT)** - Another method of encrypting DNS queries
- **Monitoring** - Track DNS changes and alert on suspicious modifications
- **Registrar Security** - Use two-factor authentication for domain registration accounts
