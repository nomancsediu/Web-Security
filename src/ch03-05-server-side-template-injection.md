# Server-Side Template Injection (SSTI)

Server-Side Template Injection occurs when user input is embedded directly into a server-side template engine (like Jinja2, Twig, or Freemarker) rather than being passed as data. This allows attackers to inject template directives that can execute arbitrary code on the server.

## Detection

Try injecting template syntax like `{{7*7}}` and observe if the output contains `49`. If it does, the application may be vulnerable to SSTI.

## Prevention

- Never embed user input directly in templates
- Pass user input as data parameters to the template
- Use sandboxed template environments
- Keep template engines updated
