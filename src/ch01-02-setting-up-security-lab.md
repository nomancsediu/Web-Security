# Setting Up Your Security Lab

Before you can practice web security, you need a safe place to do it. You cannot just go around testing attacks on random websites. That is illegal and you could get into serious trouble. What you need is your own lab environment where you can break things, learn from it, and not worry about consequences.

## Why Do You Need a Lab?

Think of it like learning to drive. You do not start on a busy highway. You start in an empty parking lot where it is safe to make mistakes. A security lab is your empty parking lot.

A lab gives you:

- **Legal safety.** You own the systems. You can test whatever you want.
- **Control.** You can set up specific vulnerabilities and practice against them.
- **Freedom to fail.** You can break things without affecting anyone.
- **Repeatability.** You can reset and try again as many times as you need.

## The Tools You Will Need

Let me walk you through the essential tools. Do not worry about getting everything at once. Start with the basics and add more as you go.

### A Good Web Browser

You already have one. But for security work, you want to use it with some extra tools:

- **Firefox** with extensions like FoxyProxy, Cookie Manager, and Wappalyzer
- **Chrome** works too, but Firefox is more popular in the security community

### An Intercepting Proxy

This is probably the most important tool. It lets you see and modify every request between your browser and the server.

- **Burp Suite Community Edition** is the most widely used. It is free and powerful.
- **OWASP ZAP** is a great free alternative. Open source and beginner friendly.
- **mitmproxy** is for people who prefer the command line.

### Vulnerable Practice Applications

These are applications intentionally made vulnerable so you can practice safely. Think of them as punching bags for security training.

- **DVWA** (Damn Vulnerable Web Application) is a classic. Simple PHP app with different difficulty levels.
- **Juice Shop** by OWASP is a modern Angular application. It looks like a real app but is full of vulnerabilities.
- **WebGoat** is another OWASP project. More structured lessons.

### Network Tools

These help you understand what is happening at the network level:

- **Nmap** for scanning ports and services
- **Wireshark** for analyzing network traffic
- **curl** for making HTTP requests from the terminal

### Other Useful Tools

- **SQLMap** for automating SQL injection testing
- **dirb** or **gobuster** for discovering hidden directories
- **hashcat** or **John the Ripper** for password cracking practice

## The Easiest Way: Docker

If Docker is installed on your machine, you can spin up vulnerable applications in seconds. No complicated setup needed.

```bash
# Start DVWA
docker run -d -p 80:80 vulnerables/web-dvwa

# Start Juice Shop
docker run -d -p 3000:3000 bkimminich/juice-shop

# Start WebGoat
docker run -d -p 8080:8080 -p 9090:9090 webgoat/webgoat
```

That is it. Open your browser and you are ready to practice. When you are done, just stop the container. No mess, no cleanup.

## Online Practice Platforms

If you do not want to set anything up locally, there are online options too:

- **HackTheBox** has machines you can hack into. Great for practicing real world scenarios.
- **TryHackMe** is more beginner friendly with guided paths.
- **PortSwigger Web Security Academy** is free and created by the makers of Burp Suite. Highly recommended.

## A Word of Advice

Start simple. Do not try to set up every tool at once. Get Burp Suite or ZAP, pick one vulnerable app, and start playing around. You will learn more by doing than by reading about tools.

And I cannot stress this enough: **only practice on systems you own or have permission to test.** Everything in this section is about setting up your own safe environment. Never test on production systems without authorization.

Alright, your lab is ready. Let us look at what the security landscape looks like right now.