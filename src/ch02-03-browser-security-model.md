# Browser Security Model

The web browser is the primary interface through which users interact with web applications. Understanding the browser's security model is crucial because many attacks exploit browser behaviors and the boundaries the browser enforces between different web origins.

## The Same-Origin Policy (SOP)

The Same-Origin Policy is the cornerstone of browser security. It restricts how a document or script loaded from one origin can interact with a resource from another origin. Two URLs have the same origin if they share the same protocol, host, and port.

For example:
- `https://example.com/page1` and `https://example.com/page2` — Same origin
- `https://example.com` and `http://example.com` — Different origins (different protocols)
- `https://example.com` and `https://api.example.com` — Different origins (different hosts)
- `https://example.com` and `https://example.com:8080` — Different origins (different ports)

The SOP prevents a malicious website from reading data from another website you have open in your browser. Without SOP, any website could read your bank balance, private messages, or other sensitive data from other tabs.

## The Sandbox Model

Browsers implement a sandbox model that restricts what web code can do:

- JavaScript cannot directly access the filesystem
- JavaScript cannot make arbitrary network connections (only to the same origin or via CORS)
- Plugins run in a separate process with limited permissions
- GPU access is mediated through safe APIs like WebGL

## Cross-Origin Mechanisms

The browser provides controlled mechanisms for cross-origin interaction:

- **CORS** (Cross-Origin Resource Sharing) - Allows servers to explicitly permit cross-origin requests
- **postMessage** - Allows safe cross-origin communication between windows/iframes
- **JSONP** - A legacy technique (now considered insecure) for cross-origin data loading

## Browser Storage

Browsers provide several storage mechanisms, each with different security properties:

- **Cookies** - Sent with every HTTP request to the domain; can be secured with HttpOnly, Secure, SameSite flags
- **localStorage/sessionStorage** - Not sent automatically; accessible via JavaScript; same-origin scoped
- **IndexedDB** - A full database in the browser; same-origin scoped
- **Cache API** - Used by service workers; same-origin scoped

Each storage mechanism has different security implications that must be understood to use them safely.
