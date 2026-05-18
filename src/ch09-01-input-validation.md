# Input Validation and Sanitization

Input validation is the first line of defense against many web attacks. All data from the client should be considered untrusted until validated.

## Validation Strategies

- **Whitelist validation** - Only allow known-good input patterns
- **Blacklist validation** - Block known-bad patterns (less effective)
- **Type checking** - Ensure data matches expected types
- **Length limits** - Enforce minimum and maximum lengths
- **Range checks** - Validate numeric ranges

## Where to Validate

- Client-side (for UX only, never trust it)
- Server-side (mandatory, the real defense)
- Database constraints (as a safety net)

## Sanitization vs Validation

Validation checks if input is acceptable; sanitization cleans input to make it acceptable. Use both: validate first, then sanitize as needed.
