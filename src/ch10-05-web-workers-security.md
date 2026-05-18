# Web Workers Security

Web Workers run JavaScript in background threads, providing performance benefits but also introducing security considerations.

## Security Considerations

- Workers operate under the same origin policy
- Dedicated workers can only be created from the same origin
- Shared workers and service workers have broader scope
- Workers can make network requests subject to CORS
- Service workers can intercept and modify requests

## Service Worker Security

- Service workers can only be registered over HTTPS
- They have a scoped impact based on their registration path
- Cache poisoning through service workers is a concern
- Always validate and sanitize data in service worker responses
