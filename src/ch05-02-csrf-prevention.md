# CSRF Prevention Techniques

Several effective techniques exist for preventing CSRF attacks.

## Anti-CSRF Tokens

A unique, unpredictable token is generated for each session or form and included as a hidden field. The server validates the token before processing the request.

## Double Submit Cookie

The CSRF token is sent both as a cookie and as a request parameter. The server verifies they match. This is stateless and easier to implement.

## Additional Measures

- Verify the Origin and Referer headers
- Require re-authentication for sensitive actions
- Use custom request headers (X-Requested-With)
- Implement rate limiting on sensitive endpoints
