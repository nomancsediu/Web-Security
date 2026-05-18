# Clickjacking

Clickjacking (UI redressing) tricks users into clicking on something different from what they perceive. An attacker loads the target site in a transparent iframe and overlays it with deceptive UI elements.

## Prevention

- Use `X-Frame-Options: DENY` or `X-Frame-Options: SAMEORIGIN`
- Use CSP `frame-ancestors` directive
- Implement frame-busting JavaScript (less reliable)
- Use the `sandbox` attribute on iframes you control
