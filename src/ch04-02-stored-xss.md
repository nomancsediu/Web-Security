# Stored XSS

Stored XSS (also known as persistent XSS) occurs when malicious input is stored on the server and later displayed to other users without proper encoding. This is the most dangerous form of XSS because it affects all users who view the compromised content.

## How It Works

1. An attacker submits malicious content (e.g., in a comment or profile field)
2. The server stores the content without sanitization
3. Other users view the page containing the malicious content
4. Their browsers execute the injected script

## Prevention

- Sanitize and encode all user-generated content on output
- Use HTML sanitization libraries (DOMPurify, bleach)
- Implement Content Security Policy
- Use HTTP-only cookies for session identifiers
