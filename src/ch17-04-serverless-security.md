# Serverless Security

Serverless architectures remove server management but introduce new security considerations.

## Security Concerns

- Function-level access control
- Event injection via triggers
- Dependency vulnerabilities in function packages
- Inadequate logging and monitoring
- Cold start implications for security checks

## Best Practices

- Validate all event input
- Use least-privilege execution roles
- Keep function dependencies minimal and updated
- Implement function-level authentication
- Monitor function execution and anomalies
