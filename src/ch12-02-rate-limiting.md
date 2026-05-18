# Rate Limiting and Throttling

Rate limiting controls the number of requests a user can make within a time period, protecting against abuse and denial of service.

## Algorithms

- **Fixed window** - Simple but allows bursts at window boundaries
- **Sliding window** - Smoother than fixed window
- **Token bucket** - Allows controlled bursts
- **Leaky bucket** - Smooths request rate

## Implementation

Rate limits should be applied at multiple levels:
- Per IP address
- Per user/account
- Per API endpoint
- Globally
