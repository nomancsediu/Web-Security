# TLS/SSL Deep Dive

Transport Layer Security (TLS) is the protocol that secures HTTP traffic, creating HTTPS. Understanding TLS is essential for web security.

## TLS 1.3 Handshake

1. Client sends supported cipher suites and key share
2. Server responds with cipher suite, certificate, and key share
3. Both derive shared keys
4. Encrypted communication begins

## Key Concepts

- **Cipher suites** - Combinations of key exchange, authentication, encryption, and MAC algorithms
- **Certificate chains** - Hierarchical trust model
- **Perfect forward secrecy** - Compromising long-term keys doesn't compromise past sessions
- **ALPN** - Application-Layer Protocol Negotiation for HTTP/2
