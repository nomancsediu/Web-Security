# Understanding CSRF Attacks

CSRF works by exploiting the way browsers handle cookies and authentication tokens. When a user is authenticated, their browser automatically includes session cookies with every request to that domain.

## Attack Example

A user is logged into their bank at bank.com. They visit a malicious site that contains an image tag pointing to a transfer URL. The browser sends the request with the user's session cookie, and the bank processes the transfer because the request appears legitimate.

## Prevention

- Use anti-CSRF tokens in forms
- Verify Origin and Referer headers
- Set SameSite attribute on cookies
- Require re-authentication for sensitive actions
