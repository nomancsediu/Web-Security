# DOM-Based XSS

DOM-based XSS is a variant where the vulnerability exists entirely in the client-side code. The malicious payload is executed as a result of modifying the DOM environment in the victim's browser, without the payload ever being sent to the server.

## Example

```javascript
const name = new URLSearchParams(window.location.search).get('name');
document.getElementById('greeting').innerHTML = 'Hello, ' + name + '!';
```

An attacker could craft: `?name=<img src=x onerror=alert(1)>`

## Prevention

- Avoid using dangerous sinks like innerHTML, eval, document.write
- Use textContent instead of innerHTML when possible
- Sanitize data before passing to sinks
- Use DOMPurify for HTML content
