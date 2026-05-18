# Setting Up Your Security Lab

Before you can practice web security techniques, you need a safe and legal environment to experiment in. Setting up a security lab allows you to practice attacks and defenses without risking legal consequences or harming real systems.

## Why a Lab Environment?

Practicing web security on live systems without permission is illegal. A lab environment provides:

- **Legal safety** - You own the systems and can test them freely
- **Control** - You can configure specific vulnerabilities to practice against
- **Isolation** - Your experiments cannot affect production systems
- **Repeatability** - You can reset and try again as many times as needed

## Essential Tools

Here are the tools you will need for your security lab:

### Web Browser
A modern web browser with developer tools is essential. We recommend:
- Firefox with the following extensions: FoxyProxy, Cookie Manager, Wappalyzer
- Chrome with Burp Suite Proxy

### Proxy and Intercepting Tools
- **Burp Suite Community Edition** - The most popular web security testing tool
- **OWASP ZAP** - A free, open-source alternative to Burp Suite
- **mitmproxy** - A command-line intercepting proxy

### Vulnerable Practice Applications
- **DVWA** (Damn Vulnerable Web Application) - PHP-based vulnerable app
- **WebGoat** - OWASP's intentionally vulnerable application
- **Juice Shop** - A modern vulnerable web application
- **HackTheBox** - Online platform with vulnerable machines

### Network Tools
- **Nmap** - Network scanner
- **Wireshark** - Network protocol analyzer
- **curl** - Command-line HTTP client

### Setting Up with Docker

The easiest way to set up vulnerable applications is using Docker:

```bash
# Run DVWA
docker run -d -p 80:80 vulnerables/web-dvwa

# Run Juice Shop
docker run -d -p 3000:3000 bkimminich/juice-shop

# Run WebGoat
docker run -d -p 8080:8080 -p 9090:9090 webgoat/webgoat
```

With Docker, you can spin up vulnerable applications in seconds and destroy them when done, keeping your lab clean and portable.
