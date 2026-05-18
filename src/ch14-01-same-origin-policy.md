# Same-Origin Policy Explained

The Same-Origin Policy is the most important security boundary in the browser. It prevents a malicious website from reading data from another website.

## What Is an Origin?

An origin is defined by the combination of protocol, host, and port:

- `https://example.com:443` and `https://example.com:443` - Same origin
- `https://example.com` and `http://example.com` - Different (protocol)
- `https://example.com` and `https://api.example.com` - Different (host)

## What SOP Restricts

- DOM access across origins
- XMLHttpRequest and fetch responses
- Cookie and storage access

## What SOP Does NOT Restrict

- Embedding images, scripts, stylesheets
- Form submissions
- Navigating the top-level window
