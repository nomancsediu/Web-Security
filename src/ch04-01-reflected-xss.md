# Reflected XSS

Reflected XSS occurs when malicious input is included in the immediate response from the web application. The attack is reflected off the web server. This typically happens through URL parameters or form inputs that are displayed back to the user without proper encoding.

## How It Works

1. An attacker crafts a URL containing malicious JavaScript
2. The victim clicks the link (often through phishing)
3. The server includes the malicious input in the response
4. The victim's browser executes the script

## Example

A search page that reflects the query parameter: `https://example.com/search?q=<script>alert('XSS')</script>`

If the search term is displayed without encoding, the script executes.

## Prevention

- Encode output based on context (HTML, JavaScript, URL, CSS)
- Use Content Security Policy headers
- Validate and sanitize input
- Use modern framework auto-escaping features
