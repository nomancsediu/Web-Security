# HTTP and HTTPS Fundamentals

HTTP is the language of the web. Every time you visit a website, click a link, or submit a form, your browser is speaking HTTP to a server. If you want to understand web security, you need to understand HTTP first. Period.

## The Basics: Request and Response

HTTP is simple at its core. Your browser sends a **request**, and the server sends back a **response**. That is the whole model.

A request looks like this:

```http
GET /profile HTTP/1.1
Host: example.com
Cookie: session=abc123
```

And a response looks like this:

```http
HTTP/1.1 200 OK
Content-Type: text/html
Set-Cookie: session=abc123; Secure; HttpOnly

<html>Hello there</html>
```

Every request and response has three parts:

1. **The start line.** For requests, this is the method, URL, and version. For responses, this is the status code.
2. **The headers.** These are key value pairs that carry metadata. Things like what type of content is being sent, who is authenticated, what cookies to set.
3. **The body.** This is the actual data being sent. Not all requests and responses have a body.

## HTTP Methods

Methods tell the server what kind of action you want to perform. The most common ones:

- **GET** means "give me this resource." You use it when you visit a URL or click a link. It should not change anything on the server.
- **POST** means "here is some data, process it." You use it when submitting a form or creating something.
- **PUT** means "replace this entire resource with what I am giving you."
- **PATCH** means "update part of this resource."
- **DELETE** means "remove this resource."

From a security perspective, here is the important part: **some applications only protect POST endpoints but forget about GET, PUT, or DELETE.** Always make sure access controls are applied consistently across all methods.

## Status Codes

The server tells you what happened using status codes. Here are the ones you will see most often:

- **200 OK** means everything worked
- **301 Moved Permanently** means the resource has a new URL
- **302 Found** means temporary redirect
- **400 Bad Request** means you sent something invalid
- **401 Unauthorized** means you need to log in
- **403 Forbidden** means you are logged in but not allowed to do this
- **404 Not Found** means the resource does not exist
- **500 Internal Server Error** means something broke on the server

Security tip: sometimes applications leak information through error messages. A 500 error that shows a stack trace is telling the attacker way too much about your system.

## Headers You Should Know

Headers carry a lot of important information. Here are the ones that matter most for security:

- **Authorization** carries authentication credentials
- **Cookie** sends stored cookies to the server
- **Set-Cookie** tells the browser to store a cookie
- **Content-Type** says what kind of data is in the body
- **Referer** tells the server which page you came from
- **Origin** indicates where the request originated from, used for CORS

Attackers love headers. They can manipulate headers to bypass security controls, steal information, or trick servers into doing unexpected things.

## HTTPS: HTTP with Encryption

Plain HTTP sends everything in readable text. If someone is on the same network as you, they can read every request and response. Your passwords, your cookies, your data. All visible.

HTTPS fixes this by adding TLS encryption on top of HTTP. This gives you three things:

1. **Confidentiality.** Nobody can read your data in transit.
2. **Integrity.** Nobody can modify your data without you knowing.
3. **Authentication.** You can verify you are talking to the real server, not an impostor.

Without HTTPS, an attacker on the same WiFi network as you can intercept and modify your web traffic. This is called a **man in the middle attack** and it is surprisingly easy to pull off.

## The TLS Handshake

When you connect to an HTTPS site, this is roughly what happens:

1. Your browser says hello and tells the server what encryption methods it supports
2. The server responds with its certificate and chosen encryption method
3. Your browser verifies the certificate is valid and trusted
4. Both sides generate session keys
5. Encrypted communication begins

All of this happens in a fraction of a second. You do not even notice it.

## Common HTTPS Mistakes

Just having HTTPS is not enough. You have to configure it properly:

- **Using old TLS versions.** TLS 1.0 and 1.1 are broken. Only use TLS 1.2 or 1.3.
- **Weak cipher suites.** Not all encryption methods are equal. Some are broken and should be disabled.
- **Mixed content.** If your HTTPS page loads resources over HTTP, attackers can modify those resources. Everything should be HTTPS.
- **Missing HSTS.** Without the Strict Transport Security header, browsers might still try HTTP first before upgrading to HTTPS. That first HTTP connection is vulnerable.
- **Self signed certificates.** These might encrypt traffic but they do not prove identity. Anyone can create one. Only use them for development, never in production.

## Key Takeaways

- HTTP is the foundation of all web communication. Understand it well.
- Every request and response has a method, headers, and optionally a body.
- HTTPS is not optional anymore. It is required for any serious application.
- Misconfigured HTTPS is almost as bad as no HTTPS at all.
- Headers are a rich attack surface. We will come back to them many times.

Now that we understand how data moves between clients and servers, let us look at how domain names get resolved and why that matters for security.
