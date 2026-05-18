# Browser Security Model

Your browser does a lot more than just render web pages. It is actually a security gatekeeper. It enforces rules about what code on one website can and cannot do with data from another website. These rules are what keep you safe when you have your bank open in one tab and a sketchy website in another.

Understanding the browser security model is crucial because many attacks happen when these rules are bypassed or misunderstood.

## The Same Origin Policy (SOP)

This is the big one. The Same Origin Policy is the most important security boundary in the browser. It says that a web page can only access data from the same origin. It cannot access data from a different origin.

So what counts as the same origin? Two URLs have the same origin if they share the same **protocol**, **host**, and **port**.

Let me show you some examples. Let us say our base URL is `https://example.com/page`:

| URL | Same Origin? | Why |
|---|---|---|
| `https://example.com/other` | Yes | Same protocol, host, port |
| `http://example.com/page` | No | Different protocol (http vs https) |
| `https://api.example.com/page` | No | Different host |
| `https://example.com:8080/page` | No | Different port |

Why does this matter? Because without the Same Origin Policy, any website you visit could read your data from any other website you have open. A malicious site could read your bank balance, your emails, your private messages. The SOP prevents that.

## What SOP Restricts

The Same Origin Policy blocks:

- **Reading DOM** of a different origin. Your JavaScript cannot read the content of an iframe from another site.
- **Reading responses** from fetch or XMLHttpRequest to a different origin.
- **Accessing cookies** and storage from a different origin.

## What SOP Does NOT Restrict

This is where it gets interesting. The SOP does allow some cross origin interactions:

- **Embedding resources.** You can load images, scripts, and stylesheets from any origin. That is why CDNs work.
- **Submitting forms.** You can submit a form to a different origin. This is actually how CSRF attacks work.
- **Navigation.** You can link to and navigate to any origin.

These exceptions exist because the web would not work without them. But they also create attack opportunities, which we will explore in later chapters.

## Cross Origin Mechanisms

The browser provides controlled ways to do cross origin things safely:

### CORS (Cross Origin Resource Sharing)

CORS is a way for servers to explicitly allow cross origin requests. The server sends headers like `Access-Control-Allow-Origin` to tell the browser "yes, this origin is allowed to read my data." We will dive deep into CORS in Chapter 14.

### postMessage

The `window.postMessage` API allows two windows from different origins to communicate. The receiving window can check the origin of the message and decide whether to trust it.

### JSONP

This is an older technique that is mostly obsolete now. It works by dynamically creating script tags that call a callback function. It is insecure and should not be used in new projects. I am only mentioning it because you might see it in older codebases.

## Browser Storage

Browsers give you several ways to store data, and each has different security properties:

### Cookies

Cookies are sent with every HTTP request to the matching domain. They can be protected with:
- **Secure** flag: only sent over HTTPS
- **HttpOnly** flag: not accessible via JavaScript
- **SameSite** flag: controls cross site behavior

If you do not set these flags, cookies are vulnerable to theft and misuse.

### localStorage and sessionStorage

These are key value stores that are not sent with requests. They are scoped to the origin and accessible via JavaScript. That means XSS attacks can steal data from them. Never store sensitive data like tokens in localStorage if you can avoid it.

### IndexedDB

A full database in the browser. Same origin scoped. Same XSS risk as localStorage.

### Cache API

Used by service workers to cache responses. Same origin scoped.

## The Sandbox

Browsers run web code in a sandbox. This means JavaScript cannot:

- Access your filesystem directly
- Make arbitrary network connections
- Access hardware without permission
- Interact with other applications on your computer

The sandbox is not perfect, and browser vulnerabilities do get discovered. But it is a strong baseline of protection.

## Key Takeaways

- The Same Origin Policy is the most important browser security boundary.
- Same origin means same protocol, host, and port.
- SOP restricts reading data across origins but allows embedding and form submission.
- CORS, postMessage, and JSONP are mechanisms for controlled cross origin interaction.
- Browser storage has different security properties. Choose wisely based on what you are storing.
- The browser sandbox prevents web code from accessing your system directly.

Now let us look at cookies, sessions, and tokens, which are how web applications remember who you are.
