# Docker Security

Docker containers provide isolation, but they are not inherently secure by default. Proper configuration and best practices are essential.

## Best Practices

- Use minimal base images (distroless, Alpine)
- Run containers as non-root users
- Use multi-stage builds
- Scan images for vulnerabilities
- Use read-only filesystems where possible
- Limit container capabilities
- Use resource limits
- Never store secrets in images
