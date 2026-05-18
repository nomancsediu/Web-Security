# DNS and Domain Security

DNS stands for Domain Name System. You can think of it as the phonebook of the internet. When you type `example.com` into your browser, DNS is what translates that into an IP address like `93.184.216.34` that computers can actually use.

Most people never think about DNS. It just works in the background. But from a security perspective, DNS is incredibly important. If an attacker can manipulate DNS, they can redirect your traffic to a fake server without you ever knowing.

## How DNS Resolution Works

Let me walk you through what happens when you type a URL:

1. Your browser checks its own cache first. Has it looked up this domain recently?
2. If not, it asks your operating system's DNS resolver.
3. The resolver checks its cache. Still nothing? It asks your ISP's recursive DNS server.
4. The recursive server checks its cache. If it does not know either, it starts walking up the DNS hierarchy.
5. It asks the root server, which points it to the TLD server (like `.com`).
6. The TLD server points it to the authoritative server for that domain.
7. The authoritative server gives the actual IP address.
8. The result gets cached at every level along the way.

This whole process usually takes milliseconds. But there are security risks at every step.

## DNS Security Threats

### DNS Spoofing (Cache Poisoning)

This is when an attacker corrupts a DNS cache so that a domain name points to the wrong IP address. Instead of going to your bank's website, you go to a fake site that looks identical. The attacker steals your credentials and you never realize it.

### DNS Amplification Attacks

Attackers can use open DNS resolvers to launch massive DDoS attacks. They send small DNS queries with the victim's IP as the source address. The DNS server sends large responses to the victim, overwhelming their network.

### Domain Hijacking

If an attacker gains control of your domain registration account, they can change the DNS records to point to their own servers. This is devastating. Your entire online presence is now under their control.

### Subdomain Takeover

This one is sneaky. Say you have a subdomain like `blog.example.com` that points to a service like WordPress or AWS. If you stop using that service but forget to remove the DNS record, an attacker might be able to claim that subdomain on the service provider. Now `blog.example.com` serves their content, not yours.

## How to Defend Against DNS Attacks

### DNSSEC

DNSSEC adds cryptographic signatures to DNS records. This way, your browser can verify that the DNS response actually came from the legitimate domain owner and has not been tampered with. It does not encrypt DNS queries, but it ensures integrity.

### DNS over HTTPS (DoH) and DNS over TLS (DoT)

These protocols encrypt your DNS queries so that nobody on your network can see which domains you are visiting. DoH sends queries over HTTPS port 443, which makes them blend in with regular web traffic. DoT uses a dedicated port 853.

### Monitor Your DNS

Keep an eye on your DNS records. Set up alerts for any changes. If someone modifies your records, you want to know immediately, not weeks later.

### Secure Your Registrar Account

Use a strong, unique password. Enable multi factor authentication. Keep your contact information up to date. Your domain registrar account is as important as your bank account.

## Key Takeaways

- DNS translates domain names to IP addresses. It is critical infrastructure.
- DNS attacks can redirect users to fake sites without any visible signs.
- DNS spoofing, amplification attacks, domain hijacking, and subdomain takeover are the main threats.
- DNSSEC, DoH, and DoT help protect DNS queries.
- Always secure your domain registrar account with MFA.

Next, let us look at the browser itself and how it enforces security boundaries.
