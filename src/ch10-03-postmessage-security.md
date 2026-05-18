# PostMessage Security

The `postMessage` API allows cross-origin communication between windows and iframes. While it provides a safe mechanism when used correctly, improper implementation can lead to security vulnerabilities.

## Security Best Practices

- Always verify the `origin` of incoming messages
- Specify the target origin when sending messages (not `*`)
- Validate message data structure and content
- Never trust message data without validation
- Consider using structured clone algorithm limitations for defense
