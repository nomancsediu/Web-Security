# HTTP and HTTPS Fundamentals

HTTP (HyperText Transfer Protocol) is the foundation of data communication on the web. Understanding HTTP is essential for web security because many attacks exploit the properties and behaviors of this protocol.

## HTTP Basics

HTTP is a request-response protocol. A client (usually a browser) sends a request to a server, and the server sends back a response. Each HTTP request and response consists of:

- A start line (method, URL, and version for requests; status code and reason for responses)
- Headers (metadata about the request or response)
- An optional body (the actual data being sent)

### HTTP Methods

Common HTTP methods include:

- **GET** - Retrieve a resource
- **POST** - Submit data to be processed
- **PUT** - Replace a resource entirely
- **PATCH** - Partially update a resource
- **DELETE** - Remove a resource
- **OPTIONS** - Query supported methods
- **HEAD** - Retrieve headers only

Security consideration: Some applications only protect POST endpoints while neglecting GET or other methods. Always ensure access controls are applied consistently across all HTTP methods.

### HTTP Status Codes

Status codes indicate the result of a request:

- **1xx** - Informational
- **2xx** - Success (200 OK, 201 Created)
- **3xx** - Redirection (301 Moved Permanently, 302 Found)
- **4xx** - Client Error (400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found)
- **5xx** - Server Error (500 Internal Server Error)

### HTTP Headers

Headers carry important metadata. Security-relevant headers include:

- `Authorization` - Contains authentication credentials
- `Cookie` - Sends cookies to the server
- `Set-Cookie` - Server instructs the browser to store a cookie
- `Content-Type` - Specifies the media type of the resource
- `Referer` - Indicates the page that linked to the current request
- `Origin` - Indicates the origin of the request (used in CORS)

## HTTPS

HTTPS (HTTP Secure) adds TLS encryption on top of HTTP. This provides:

- **Confidentiality** - Data is encrypted in transit
- **Integrity** - Data cannot be modified without detection
- **Authentication** - The server's identity is verified via certificates

Without HTTPS, an attacker on the network can intercept, read, and modify all HTTP traffic—a classic man-in-the-middle attack.

### TLS Handshake

The TLS handshake establishes a secure connection:

1. Client sends a ClientHello with supported cipher suites
2. Server responds with ServerHello and its certificate
3. Client verifies the certificate
4. Both parties negotiate session keys
5. Encrypted communication begins

### Common HTTPS Misconfigurations

- Using outdated TLS versions (TLS 1.0, 1.1)
- Weak cipher suites
- Self-signed certificates without proper pinning
- Mixed content (HTTPS page loading HTTP resources)
- Missing HTTP Strict Transport Security (HSTS) headers
