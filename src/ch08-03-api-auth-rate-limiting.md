# API Authentication and Rate Limiting

API authentication and rate limiting are essential for protecting APIs from abuse and unauthorized access.

## API Authentication Methods

- API keys
- OAuth 2.0 Bearer tokens
- Mutual TLS (mTLS)
- HMAC signatures

## Rate Limiting Strategies

- Fixed window rate limiting
- Sliding window rate limiting
- Token bucket algorithm
- Leaky bucket algorithm

## Implementation

Use HTTP headers to communicate rate limit status:

```
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 95
X-RateLimit-Reset: 1640000000
```
